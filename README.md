<!DOCTYPE html>
<html class="staticrypt-html">
<head>
    <meta charset="utf-8" />
    <title> Wiki - Protected Access</title>
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <link href="https://fonts.googleapis.com/css2?family=Fredoka:wght@300..700&display=swap" rel="stylesheet">
    <style>
        :root {
            --clay-red: #E74C3C;
            --clay-blue: #3498DB;
            --clay-yellow: #F1C40F;
            --clay-white: #FDFEFE;
            --clay-base: #ECF0F1;
            --clay-radius: 20px;
            --clay-shadow: 8px 8px 16px rgba(0,0,0,0.1), -8px -8px 16px rgba(255,255,255,0.7);
            --clay-shadow-inset: inset 4px 4px 8px rgba(0,0,0,0.1), inset -4px -4px 8px rgba(255,255,255,0.7);
        }
        body.staticrypt-body {
            height: 100vh; margin: 0;
            background-color: #f0f2f5;
            background-image: radial-gradient(#d1d9e6 1px, transparent 1px);
            background-size: 20px 20px;
            font-family: 'Fredoka', sans-serif;
            display: flex; align-items: center; justify-content: center;
        }
        .staticrypt-form {
            background: var(--clay-white);
            border-radius: var(--clay-radius);
            box-shadow: var(--clay-shadow);
            padding: 3rem;
            max-width: 400px; width: 90%;
            text-align: center;
            border: 8px solid var(--clay-white);
            position: relative;
        }
        .staticrypt-form h1 {
            color: var(--clay-red);
            font-size: 2rem;
            margin-bottom: 2rem;
            transform: rotate(-1deg);
            border-bottom: 4px solid var(--clay-yellow);
            display: inline-block;
        }
        .staticrypt-password-container {
            position: relative;
            margin-bottom: 1.5rem;
        }
        .staticrypt-form input[type="password"] {
            width: 100%;
            padding: 1rem;
            border-radius: 12px;
            border: none;
            background: var(--clay-base);
            box-shadow: var(--clay-shadow-inset);
            font-family: 'Fredoka', sans-serif;
            font-size: 1.2rem;
            outline: none;
            box-sizing: border-box;
        }
        .staticrypt-decrypt-button {
            width: 100%;
            padding: 1rem;
            border-radius: 12px;
            border: none;
            background: var(--clay-blue);
            color: white;
            font-weight: 700;
            font-size: 1.2rem;
            cursor: pointer;
            box-shadow: var(--clay-shadow);
            transition: all 0.2s;
        }
        .staticrypt-decrypt-button:hover { transform: scale(1.05); filter: brightness(1.1); }
        .hidden { display: none !important; }
        .staticrypt-spinner-container { display: flex; align-items: center; justify-content: center; }
        .staticrypt-spinner {
            width: 3rem; height: 3rem;
            border: 0.4em solid var(--clay-yellow);
            border-right-color: transparent;
            border-radius: 50%;
            animation: spin 1s linear infinite;
        }
        @keyframes spin { 100% { transform: rotate(360deg); } }
    </style>
</head>
<body class="staticrypt-body">
    <div id="staticrypt_loading" class="staticrypt-spinner-container hidden">
        <div class="staticrypt-spinner"></div>
    </div>
    <div id="staticrypt_content" class="staticrypt-form">
        <h1>Wiki Login</h1>
        <p>Please enter the studio password to access the internal wiki.</p>
        <form id="staticrypt-form">
            <div class="staticrypt-password-container">
                <input id="staticrypt-password" type="password" placeholder="Password" autofocus />
            </div>
            <label style="display: flex; align-items: center; margin-bottom: 1rem; cursor: pointer;">
                <input id="staticrypt-remember" type="checkbox" style="width: 20px; height: 20px; margin-right: 10px;" checked />
                Remember me
            </label>
            <button type="submit" class="staticrypt-decrypt-button">DECRYPT</button>
        </form>
    </div>
    <script>
        /* 
   StatiCrypt Decryption Engine 
   Ripped from the user provided snippet for use in the A+C Animation Studios Wiki 
*/
const staticryptInitiator = ((function(){
  const exports = {};
  const cryptoEngine = ((function(){
    const exports = {};
    const { subtle } = crypto;
    const IV_BITS = 16 * 8;
    const HEX_BITS = 4;
    const ENCRYPTION_ALGO = "AES-CBC";

    const HexEncoder = {
        parse: function (hexString) {
            if (hexString.length % 2 !== 0) throw "Invalid hexString";
            const arrayBuffer = new Uint8Array(hexString.length / 2);
            for (let i = 0; i < hexString.length; i += 2) {
                const byteValue = parseInt(hexString.substring(i, i + 2), 16);
                if (isNaN(byteValue)) throw "Invalid hexString";
                arrayBuffer[i / 2] = byteValue;
            }
            return arrayBuffer;
        },
        stringify: function (bytes) {
            const hexBytes = [];
            for (let i = 0; i < bytes.length; ++i) {
                let byteString = bytes[i].toString(16);
                if (byteString.length < 2) byteString = "0" + byteString;
                hexBytes.push(byteString);
            }
            return hexBytes.join("");
        },
    };

    const UTF8Encoder = {
        parse: function (str) { return new TextEncoder().encode(str); },
        stringify: function (bytes) { return new TextDecoder().decode(bytes); },
    };

    async function encrypt(msg, hashedPassword) {
        const iv = crypto.getRandomValues(new Uint8Array(IV_BITS / 8));
        const key = await subtle.importKey("raw", HexEncoder.parse(hashedPassword), ENCRYPTION_ALGO, false, ["encrypt"]);
        const encrypted = await subtle.encrypt({ name: ENCRYPTION_ALGO, iv: iv }, key, UTF8Encoder.parse(msg));
        return HexEncoder.stringify(iv) + HexEncoder.stringify(new Uint8Array(encrypted));
    }
    exports.encrypt = encrypt;

    async function decrypt(encryptedMsg, hashedPassword) {
        const ivLength = IV_BITS / HEX_BITS;
        const iv = HexEncoder.parse(encryptedMsg.substring(0, ivLength));
        const encrypted = encryptedMsg.substring(ivLength);
        const key = await subtle.importKey("raw", HexEncoder.parse(hashedPassword), ENCRYPTION_ALGO, false, ["decrypt"]);
        const outBuffer = await subtle.decrypt({ name: ENCRYPTION_ALGO, iv: iv }, key, HexEncoder.parse(encrypted));
        return UTF8Encoder.stringify(new Uint8Array(outBuffer));
    }
    exports.decrypt = decrypt;

    async function hashPassword(password, salt) {
        let hashedPassword = await hashLegacyRound(password, salt);
        hashedPassword = await hashSecondRound(hashedPassword, salt);
        return hashThirdRound(hashedPassword, salt);
    }
    exports.hashPassword = hashPassword;

    function hashLegacyRound(password, salt) { return pbkdf2(password, salt, 1000, "SHA-1"); }
    function hashSecondRound(hashedPassword, salt) { return pbkdf2(hashedPassword, salt, 14000, "SHA-256"); }
    function hashThirdRound(hashedPassword, salt) { return pbkdf2(hashedPassword, salt, 585000, "SHA-256"); }
    exports.hashLegacyRound = hashLegacyRound;
    exports.hashSecondRound = hashSecondRound;
    exports.hashThirdRound = hashThirdRound;

    async function pbkdf2(password, salt, iterations, hashAlgorithm) {
        const key = await subtle.importKey("raw", UTF8Encoder.parse(password), "PBKDF2", false, ["deriveBits"]);
        const keyBytes = await subtle.deriveBits({ name: "PBKDF2", hash: hashAlgorithm, iterations, salt: UTF8Encoder.parse(salt) }, key, 256);
        return HexEncoder.stringify(new Uint8Array(keyBytes));
    }

    async function signMessage(hashedPassword, message) {
        const key = await subtle.importKey("raw", HexEncoder.parse(hashedPassword), { name: "HMAC", hash: "SHA-256" }, false, ["sign"]);
        const signature = await subtle.sign("HMAC", key, UTF8Encoder.parse(message));
        return HexEncoder.stringify(new Uint8Array(signature));
    }
    exports.signMessage = signMessage;

    return exports;
  })());

  const codec = ((function(){
    const exports = {};
    function init(cryptoEngine) {
        const exports = {};
        async function encode(msg, password, salt) {
            const hashedPassword = await cryptoEngine.hashPassword(password, salt);
            const encrypted = await cryptoEngine.encrypt(msg, hashedPassword);
            const hmac = await cryptoEngine.signMessage(hashedPassword, encrypted);
            return hmac + encrypted;
        }
        exports.encode = encode;

        async function decode(signedMsg, hashedPassword, salt, backwardCompatibleAttempt = 0, originalPassword = "") {
            const encryptedHMAC = signedMsg.substring(0, 64);
            const encryptedMsg = signedMsg.substring(64);
            const decryptedHMAC = await cryptoEngine.signMessage(hashedPassword, encryptedMsg);
            if (decryptedHMAC !== encryptedHMAC) {
                originalPassword = originalPassword || hashedPassword;
                if (backwardCompatibleAttempt === 0) {
                    const updatedHashedPassword = await cryptoEngine.hashThirdRound(originalPassword, salt);
                    return decode(signedMsg, updatedHashedPassword, salt, backwardCompatibleAttempt + 1, originalPassword);
                }
                if (backwardCompatibleAttempt === 1) {
                    let updatedHashedPassword = await cryptoEngine.hashSecondRound(originalPassword, salt);
                    updatedHashedPassword = await cryptoEngine.hashThirdRound(updatedHashedPassword, salt);
                    return decode(signedMsg, updatedHashedPassword, salt, backwardCompatibleAttempt + 1, originalPassword);
                }
                return { success: false, message: "Signature mismatch" };
            }
            return { success: true, decoded: await cryptoEngine.decrypt(encryptedMsg, hashedPassword) };
        }
        exports.decode = decode;
        return exports;
    }
    exports.init = init;
    return exports;
  })());

  const decode = codec.init(cryptoEngine).decode;

  function init(staticryptConfig, templateConfig) {
    const exports = {};
    async function decryptAndReplaceHtml(hashedPassword) {
        const { staticryptEncryptedMsgUniqueVariableName, staticryptSaltUniqueVariableName } = staticryptConfig;
        const { replaceHtmlCallback } = templateConfig;
        const result = await decode(staticryptEncryptedMsgUniqueVariableName, hashedPassword, staticryptSaltUniqueVariableName);
        if (!result.success) return false;
        const plainHTML = result.decoded;
        if (typeof replaceHtmlCallback === "function") {
            replaceHtmlCallback(plainHTML);
        } else {
            document.write(plainHTML);
            document.close();
        }
        return true;
    }

    async function handleDecryptionOfPage(password, isRememberChecked) {
        const { staticryptSaltUniqueVariableName } = staticryptConfig;
        const hashedPassword = await cryptoEngine.hashPassword(password, staticryptSaltUniqueVariableName);
        return handleDecryptionOfPageFromHash(hashedPassword, isRememberChecked);
    }
    exports.handleDecryptionOfPage = handleDecryptionOfPage;

    async function handleDecryptionOfPageFromHash(hashedPassword, isRememberChecked) {
        const { isRememberEnabled, rememberDurationInDays } = staticryptConfig;
        const { rememberExpirationKey, rememberPassphraseKey } = templateConfig;
        const isDecryptionSuccessful = await decryptAndReplaceHtml(hashedPassword);
        if (!isDecryptionSuccessful) return { isSuccessful: false, hashedPassword };

        if (isRememberEnabled && isRememberChecked) {
            window.localStorage.setItem(rememberPassphraseKey, hashedPassword);
            if (rememberDurationInDays > 0) {
                window.localStorage.setItem(rememberExpirationKey, (new Date().getTime() + rememberDurationInDays * 24 * 60 * 60 * 1000).toString());
            }
        }
        return { isSuccessful: true, hashedPassword };
    }
    exports.handleDecryptionOfPageFromHash = handleDecryptionOfPageFromHash;

    function clearLocalStorage() {
        const { clearLocalStorageCallback, rememberExpirationKey, rememberPassphraseKey } = templateConfig;
        if (typeof clearLocalStorageCallback === "function") {
            clearLocalStorageCallback();
        } else {
            localStorage.removeItem(rememberPassphraseKey);
            localStorage.removeItem(rememberExpirationKey);
        }
    }

    async function handleDecryptOnLoad() {
        let isSuccessful = await decryptOnLoadFromUrl();
        if (!isSuccessful) isSuccessful = await decryptOnLoadFromRememberMe();
        return { isSuccessful };
    }
    exports.handleDecryptOnLoad = handleDecryptOnLoad;

    function logoutIfNeeded() {
        const logoutKey = "staticrypt_logout";
        const queryParams = new URLSearchParams(window.location.search);
        if (queryParams.has(logoutKey)) { clearLocalStorage(); return true; }
        const hash = window.location.hash.substring(1);
        if (hash.includes(logoutKey)) { clearLocalStorage(); return true; }
        return false;
    }

    async function decryptOnLoadFromRememberMe() {
        const { rememberDurationInDays } = staticryptConfig;
        const { rememberExpirationKey, rememberPassphraseKey } = templateConfig;
        if (logoutIfNeeded()) return false;
        if (rememberDurationInDays && rememberDurationInDays > 0) {
            const expiration = localStorage.getItem(rememberExpirationKey),
                  isExpired = expiration && new Date().getTime() > parseInt(expiration);
            if (isExpired) { clearLocalStorage(); return false; }
        }
        const hashedPassword = localStorage.getItem(rememberPassphraseKey);
        if (hashedPassword) {
            if (!await decryptAndReplaceHtml(hashedPassword)) {
                clearLocalStorage(); return false;
            }
            return true;
        }
        return false;
    }

    async function decryptOnLoadFromUrl() {
        const passwordKey = "staticrypt_pwd";
        const rememberMeKey = "remember_me";
        const queryParams = new URLSearchParams(window.location.search);
        const hashedPasswordQuery = queryParams.get(passwordKey);
        const rememberMeQuery = queryParams.get(rememberMeKey);
        const urlFragment = window.location.hash.substring(1);
        const hashedPasswordRegexMatch = urlFragment.match(new RegExp(passwordKey + "=([^&]*)"));
        const hashedPasswordFragment = hashedPasswordRegexMatch ? hashedPasswordRegexMatch[1] : null;
        const rememberMeFragment = urlFragment.includes(rememberMeKey);
        const hashedPassword = hashedPasswordFragment || hashedPasswordQuery;
        const rememberMe = rememberMeFragment || rememberMeQuery;
        if (hashedPassword) return handleDecryptionOfPageFromHash(hashedPassword, rememberMe);
        return false;
    }
    return exports;
  }
  exports.init = init;
  return exports;
})());

        
        const staticryptConfig = {"staticryptEncryptedMsgUniqueVariableName":"ba04cd3a192e189f74189f9a7d0d6ba58d54dabaa4c2887617b64aeaa8a249c6bf012b5d54333f27e9dfcabfe909161a2a6f9a4c65eec14a78af56e1765a29f21b1a30a01ba9b69fa347b2838958357aee568d0505a4b8c7c1c2e17171e611e82b278dd48b8e617a64165dc806c035d3a04760747182269a29207d623a743572bbbca0df8714267b4777875395e28123e0f1fead3bc36974b8a050e90e3aebcb2b7907be68657670ec4587dabccbba692665d8ac316ff4b337d42975b96b58c6951b91fa91e1b0769896e58a9fc687ea1ae2fde27219b52098a2d26b67e3af304969ec10cced79965f8d176bf05fe99369f775c8a3621f20dbfaf1d96c064bf41797512d6aeecb6539f56e8589b5662b9aff00314a35ba29910b5b2cbbb310267ecf34797f32c7ee56bbbb2899ab2b4bfe4dd79c61f0c802fde2cdfba1322d97b6e2864ba1783c084f97aa15cd52593ba32085f482ecb5941edefc68de784e3f3afce7f098e5561c7a4db4869142853064a8c7cb52674d781bffe4942b4a51d0d1e448259ee2da2d2b9b696aa717db99cf0af93f92f33c6712130d2f2c725d4f4698140d3d3c591c98489c5328db8742960b7b73b1f1d4d0fd964812db84a69e500ece11edfdaec3b93c8acc213ff538528a7e208b8bce5a33fece7a6df157bcf75d232242fd22706a3f7eab55e594ebc8cbb95ad31c61885cdbc37d1ed1c4d7d2733e3ccd88b68ea7bd2e54a0e0b382826c39fb30bad256b27c780f19ed2bb5344c694ce8895c8801a49513695c2bdde8c7f642b63017652b293e08aed63b81cce620ff96cc8d879c6e881e0d657e3cec82d28906f5df6d95f0a2f5c92369a097f2ec4a16d2bdfa7dbed34a27708bba3f3a8cf1075a0ebb2c1cbab11fd597470b5b79e50b8d255aea71e39ace154ac801d18e21168cb3a1c9e7ec5365ae4453c4f94cc38b9182d1b11c9ca06cb68d1f6555dc72831d965021859d8a55fa52dd0de8885a23d3fbee09189de638c763e9b49621289498eec9e5dfafe62ed3bf31af122fac7140c4ba6c1ed9b4b27ec0214d43e45060f3582e332090273e8dce1645cd364775b316aa5e0cd59e1b0f0f846c734785f1abebd06dcb6c370ca77813a7176c738cd35bae4e97482925a285b33b207374990ecc480d3ac69372eddd1d21f1baace5e6ac58790ce7c217f71687b0b69d7ec28c4cdb43cdde7531ed2404c53da81f476ecaf06624920e233dbeed2e275f854ae00c16a11188140d69529da0cf3047ec7c7e5e4c6d69e7340f956a62aa02ed59719c0a88670081fe26d6f20f55d5d0f1f0dd9324a45a6f20d66ed8127243b6c58d6f2703823437b295f11da6a1088747fd9aa1119c1b48f3a6e602a0e67efd676c8292d93dfef6399e3a4c65b706c0b117471e5077780970b38b0868888c743c9a0c9d060d0ae4cc22d4ab72e02d23b53715e65847cb93fc828078f21c145c4b4e94bcfab1e8d8106e3d11acef09b18a204bb24e70cd2efcb91009b92bcfb959c08f56d652ab23c4a77c70a340707cd9264813a5554cac9676f818805d004ab00374344bb7da7b0b2f685a6271cfbcb6a85c9df3ab284ae5e650217dd6d449e9cc32e0b8a35a4a5e8d4ab6b565626b4427d2f0381b43052c70e78c5878219c70b9063d5d0a88fa3d4d5c14a6913a9eb31967523e46b2633789fa052bb058b43b17f24c45ba2f753144ad9f8db5dce20c58a31ce09df20f66548dc61480e87beb2127e33bdc81437470e280cb35af80d835beaea9f88a887805ec3730536d33d3ed8dd24274b280b19daee7afb0525da3e71f1d5a1a57238908bb4454abf36519316d60591e6e60d0b0016c7aae1ab14e9cbf8ea9abde338dad9ad36d2cde0b7d84c3a84b781976c6eaf71a90fad44e91c59bee38f0ad8be08806d4261abc121fff103ae24a567d4c98a12b1f1fd406492465fbb5f352510862f6762cee8f9ecf3703fba5c635d63bf5b231560d580aec71f596e1760a11ffdccbb6bb197e5d413f9877382a3674ee0d5bd53021e280c311c3dcd8e41475f9329ae40774c5ad85de685189f6c4d59b921996fcf801bf3b7807fdad59570c1f7bd2f6e45a42e3018f734642a06aad2a873439820dfe6718dff8634e06d3758ba4ed6d583da3212b416a1ab541ade620887689c2f0e711fa2037abf8a63552fea5fd13bc51b966e0c8056f24b6f8559eb5aa11156d2917cf383b78645ca1ffe42c1af08a5c66def172d8ede1fc161aaf907661c056a3895b79a4a01ec99dd3a148055c9e17715647a49d01d98db23216e3f801d1b5fb1afbc145ebb05c2b7a18ec6c8a7904502ef41474301e30b8d246949825336ae64152a27e2d7b807050949996cf8e5019e51c2ec553dfa52416698141e129afc71448abfef5ecf0623aa2d08c8c0a6fa3a08c769baa30506d1e1be2ec5f0677645c7b81976ce947c040d9a62d889f7e864a61fa24f765dbfc3d4b20f7e75c5dfd1e235c5f01a84614346ac40ae77a7f1c9277cfd78f4f16da3a11030c16a3cb364afce965137a1e8ad109a3b0a48b7a7b2a98ad9a4c9d31426f7c6a82ead8eba483e1cee5690fb255672a2f098ad689c49b1549a3598c1ad6160839546e8a0d2dad5b7c789d9cc43227a69acda784250fcac908c1ea9e2df972e7894ba4963968b81063c47d47810f0eea835f4eec3b60b2fbadf2092e29287c6bec6c94d8ec33e45cfe28d8fb0f9e82937d81606e9f7a39b8c679aad26bf92ddcd3c44622fa755757bdf6d4d3ceafb9d39e0d52ee3f6b0f76f28ac9ec592167afbfcc49caecd228ec3e596bcab5ec2e385f919aae0f259faaa50d8d91506216f5b69eddb24375ea93e7e2043231ea391520bab01752be9c5e19eab515ff75af886a4226f2111b3205f24053654303d91ad7860818a5122deeb6d2cb891fe4459f306ddad629cb24422e43744a5a69b81fb47b0a6351ef10fcdb350810ce0a2e9335d5265f320293e02a27fa94de9f70ae83a458304e5b89a94e3f44fe1ee29152b001fd5c504c981c6f0eb09e8bfe972e9ad96dc50c22af6a54cab987c09e16eeca447d62e1845f1533f1ccbc40e0aaa40b5a31b87671f0bec954e3db4011e0cf2668b40d3d97390951dfd936f7cbedfd237688288966792452b54d51264ee0449efe4b97783498556a47c79672b9ce9421e9f15def1c7e170f0cb83acd922c4084328be3f8322bb37c6d77e24846d251157001d8359d34d9c593da14c57b2f5ebeedde58d14cc58dd23bc379862b3128be9899e252bc6f1d9e1db2eacb817bafdf77ebef90bfb35be9ce115c41e55fb4a4d0ee19be7e9a8db53faa816d79678f33a620dfeb0aa16be69756904a8b8ada33c4f7f3ad97bb674056cdfb0f5aced9eaef95925e09f2b46d5c89321b2377091b900629e27c09967ee420b764ad74e40118ed379c396d5002cc2e9fc4f333651828a78d5b49b6541c614322f9fc8da10caced16e12fcd47e79c3fd9af901617d6799ecd060433a41f4830c32878d281a8c445b5fefda60c05bb8c4b3c41dfd2df57792cc2a8570d11312d6c34c0847069eea7339db91e6041328ed181719ea7db56bdf68e923d75970c84bd74de11ffc784a809ba1bd4485de8947f3951062b509f4bbbb80f0cbbb8ccdcabe9724b8b1de3369e1551b6e39a44e09a1972f00f7e38e77fe6f013002a577935339a962de021378e4927aeefc9890f5b7f78d27cbee9160e2884caebf184cf9ba248b2a4c2057a20da83bd8f3e7a73304460e24bfb29eb9a78fb61c0a325487f3d783a65594c6fcafe8ae3b163a3144e3566c77c32bd7fe0083f432b86e9cdaca20ddb07b3f27c9442d5abb5c3f71f93b7f4438b28931cc983660e8e5d709ddc828a1bc7a0ae96299fa2c5ca613d8e3810b88a08fabc5c8aba4d94a2150e965d4e313913c1ee5050a8f92cad806ef6b59571e0edf8324e32bce0960f5162e4b244177e0822e7c6c254a18c9e4a7aca93fa020154a2b45a276a80ae36944d5069ab0224612c9f440954f52b55d3e0482028164f4c4cc64fb491c3702d13afe2547ed0b71ed86c50f8b280cfcc2a2a2c0ff888b8ea77bd171ac75dc1375f37bb1428fdeab457362fe46e41627fd6c36858895a830035bdfad6af26d63acb30cca9dfd7bc53e277ae182b036df7021898638620fa0c2ba78b3c7d675639b05462c2680dcc6593ba85ee76f37c29bf8eab3e6d3b9f3790cd608220d37ada18eb1a1821c7c53503ffd20af27d4da9a74b3eff4f2748a24179d2de43d97e820e90a2264c8df5cc1dcac04fafb1156589a73fe7fcdfe188171dabe5d6f8eb8b24f1060d66d5d643d9d8fb4f3a615338a42c0cd77db0e1935ce5cab2ba851246662e0f191c2b016089295604568340f61bd8b50101e10a988d9249ede156272ced01404d354d033ffc4ce3217a716c225f6d9656e62f2c87ab92e6d9b0705629e1005501586f1aeca21c77ff841b58a50e025cc928a11da76514999717312e7073289db173a6cf3dabadbd5a280e1c9fc23ec5ed4c5ff012116dfe9afcf8df9c38ec02568faa0ea2f054475a1378c1af51690ead16dda7600ce465a0a31ef78ecc65c7e0685742bef7515cfe04b1a219911502684e077420d34e11ddc299646e257c415e557fcb5660539d08413fd65602a263f4c5f65bcb3e6abac98505912d00b50b1cc560ebebd4b53deb253524b28ae0169d065c5bdd739c46aa54ebca39c3a5dd3e911ddbb173715266071a209f9930bf66fb755130a638d7d69cf6e41742e206e1f4e0711575dddfaac3b9207fbab281c8013dfda068f6c491acca04803be24cf482f2732416e6906d3cf0f2684bcba9fc91dbd4564bae1c54fdcb6c46cee5fbfd8620fba0988bad5d9c59f1d3bdcd2647a0c0712a898feb5ea30408f302a3ab4a9a51db1ae3f42534ee47c53d9fe5db8b259ddd0c77015e3a65a32c38a76f1ab391f59a0fb40b42f79097ce837e2a9f6850b382ee92c3caf38677436e92f373735c3d05b1a5ad8436e4881423a83b9dbfdd9276f705f86d556405f9465200528d4fff9814db9b075dc78765018f360a44ffe9d68a51991d30f84c8d95dea604cbcfcc89cca2f60804fdad14aa9be223dc12055b8f1321248180a5d9cea7244894882b1afd6caf625608ac7554d94d473b99b68215e0c703ccfae021e54117d6538e0c45a8daab3891452cbd739776212d3435ffe0f67c91886586ab0c3147bee383b08e5e2d362ea91a0d1b07efdbc155ddaf0f5cd405d68d820f63ccdfe1aa43e94befb0e98dd4a9d03305f99e6a11cfb133fd78f3f92b3854b2938072b7ae57ae94227cce86bd7eb938768a34724c41a0ba891a8f85c95588ba7c894ed3616f0b75f983aece57459581d3d2c64d9c30a1a7fab3ba818c4342ef8d5195f650a7c7ba1df9e6437d05e72ea111d8889187c18686319827f19432827b0e61a0702a4ca4ab79f88a992de7376cfb9ea7713caadf591b3c5c1495669d36fa10da2e79b7accd55478ed2663886dc92e48e010eeb03b84af2881128a3454781e6d8f5c46327e9e709a3b1559994946fce42efa5a1c7a4070f425f5eb7f61a1b08aad4a8079a89d678df3b184464e37931b6f5996a4c513ff2aeda873e9c2e11817e1b1c80537e9ca8ec875fdfb4175b0e8cd59e747e0368014bb68a30e359b31805c517ad27f1580a9f628e2f1e37ea5b23016937a1d0ad52780da029db942ed37b6e94ad7bbeb24437d667ca363d9923e9195308528713fd4dee6a2347f3605e8c089d016c0c8c342a1f705d3b620b5480755ceba037c125b74eb9a3287db2cc81aab9cb21df5d4e9fc552a880fad4afdd0184fcbafba50ef8c3dfa96f57b57f81763467cef455385a7a6994e6dbdc0cddb3dec40aadab83e305c8d46f048e2040f3eaa97bf045549d5f3ad2b7643f8988729cf24375474faf4c937d9fcbdc2e54e7c36677845a70681a671cf41c4fe1e0e50398b006bfeba3006ea8229a27970491f681f93e97f7c381f7a28159e5870ad1891abd720bcb5405edd4284cc2b4699f61f53f9b6d9b5212054fecd8c5562aac625a17365a4493dff3eebbff78edaa24ff1553ae81d8bd6b137193223cc556477e60bc67cce80a3fa566d42da27631343a60adb15f22b567d8dfced3361985c248acacb4257c96d7dbd322d241505542be20af86e080b89c155ced491b066afcc6622b2e1619f2fbb5cede86ef014867dc8839a305f6850a4d7436b9a5cbb0cce25943c432d4d42eba350a06cc2539d1c374b94005612848abce46615a53649f28d48f21963775078d665105e4542ea99244c06c6cfa87d1409decdf6d5c382d7ee04c52ce278ceef5dc59d5f51662ab0b8ce5c8b04190a1bb8e72b6dd6fcbf62b0ffe27a1e301059498614c7181aecb34229f8baca63c6e91f7dff779acd1801ff66f2f8dc83d4d6a1b50e3bfddbb5582aa0dccaac8591b8cfda5380db82c715a5432762033e83c3206313eb3733080a736e025a018df5be3b55b9ebc4a961b838c3d247921d2bca617bc1f66b8667e47c0848905527bbe20e09cd4c3239f0ceb709c9e4712469e564176f8a5fb8a02b32901b2e6e86146e51106a7c3cdd660c87f327166f4b5e18e1be4b2a6055a772aa929033df65dceb432298917a966f418ed8d783c0d548addb2cc5caee59aeacf396908a9db433a49f9de3a9ace378db2a7dffe15328f6a571e4a13ac291900f160970ea82b5bc15d7c7faa784747a1174ac9e2b4808f751b4dc96880c1fee8927515e9a4537b539f96f851a6cfc67391c57f8bb18e83d1dc4930a5b492903bba6643d785121d48469602448acfcd88d70d8e5dab118dd9e8214c164ec248caa7d85211626038bc0e2fc04217ca049cf3f71d88edbbc6813cdfb4d01066c634a94da84e47b8795f86edfbc222e394efb80c2e5d226bef870fe6b90677bae36d174f93253497ba33043234ab197dc613cc53f8ace9ee9135add56e5d3cc7689f4c838ff965e5c533818d35d3b4bc80a18fde67fd9d3ce3124af10666553692794cb3653694eceb3e2514a70453ca9d15a8987a066709005305fed2a9bee15bab6aab1404efba3850415eb9990258ef8ce5949359745464bd20fa882d1c58ccd790c859bfeb35798e2b223bc30ec0a6ef37ef7703e936e04b1c86fedca9fbf9935295e3799307b1eb5bf8ce54f3f6c7b29d21c97b5f7c70355548f0856d8da8d101327ec16cad45ef5557a2d90bfc95d12d6b2ff5a8f5934587a0131bb5d0bb9b5916da9a3e738b7b7eaae819d962dbcf133a0392d78158de4cccef1854c64d650ff60a7c40b2ad19c2b1e33a6cc7db7f26b5f0583c03919c869445a2468d3ed510f0f05a3c7a4ce0bead4741624449d919e8871f8233a9d135461a19188c762141e220fa1920952bde636146ecbb390d9fbd8956790e983cfb60a90b7b8158de0bdefd66f6fddf22a244786bea367efe1e9f7ae6d9e230c5a320f8614571a338c2893d3535d0a01443c95f65fb4fc89af56b6a954a90d6f236cb1b0cadfa92eecbfdba9d87587aa977942762b6fbd032f00eb3d4c5ba369a06f48567b2a897e64eb88b218c7f0250305ff22d80766114d653a5f97912e898ae2e9c0342da4dbea214ffa501547c4d6a11ef04125b0e9b7c5eb3b38d23669c27d660b63fa74ce9c8df401f0cbbb3040a899d37e02db5b33aaf01924202eb8de0e13aaf5f5612e3d73d093d262a8c851ed610319215dc4b8232f43537e4c8693490a4abaa41bfb60abf5d9fa9ae0386bbfd0f6596792d6ca3c4468652c4f5a40db3a40ce80f18a86857f5ce941b7daaaf1d1fe4e71e7846ca2de5d1287002151bbbd7a3eb0a1b71a14ee5d6325568862569c6aa8b7b844f9da1924b26eb2676f4bc0b3163b767aebcd8f75ea9df5789a3cfc6e58e8652a6e39a2128c337ba1fbc9ed8a0414b9c7ce296af7b63e2cb515e9b29ad474cff6f721ccd8e610d73cf13f7a5d9ddf174f4780dddff29261a18ceb7304981b6d4c13d7ecffb17d526c9710e04838f9a7de457929a882cc819a3566acb582585bc3027e5bcdbd1da6236fa80034d076d2e56b60ebb5e77813d0384cc3d0b502e0051439d1205bf927cb46f1b5b70cf1402655b2d195028b1d327ee8090538d52558b2087a0a5c1d58f881cb749ef639c0b0ed68ea401cb93c123eb5c32de24762688d0b5f36e73c93d31acb0a195f7182f4380cfaa91199ddf60b57a302a8c701418bc58374ad4f63c2d5240debccd1e93a78b475333b724e51688f7c3f3180189255927bc37a32e1a8197810056c9b38a73bd7a95444087ab8c03ecd6d0db162dc50f732a8b34b024179f2cf9654bf566c58cf4edd5bf97468e000540bc2fcbd87c564623ec4aa61677c6003a4acc7ea1bf56bd6876d31aa53e1873b541c62eeaf387c07cb8a544420727419a246bf9b592b5563a68ec8b42c466489591c217aa56f5e9de7fc3064bff74444eb884de945ea7f9e2307db11b6620b287a4800bd5248b230a15ce8aa7fc20fc044690aa7dc84955ce398ac4be6e6a58823290ee4f69ebf1bdbf9922db1aeced2be1666bf90122bbafea30e1ee126f233654c281f5e28f2221a47eda8c9dd11bee6ef64c4a3eae85a6ae9bb1de4d6708b2eeb03b5bfda887e19be312485e3246cbcdf8119e014cca395e22840c43d7c874856ed305d81f4df1ea7681c6fce0a4d7ad01b30d3e2feb10823b0b62fc4de63fa093cd15a90f35f2564b4fa55e268b5fa71babeb32c9067da2387c8c7adf3c3113969547781a9c456a4fd35a250ecc73a60486f024edffdefbaa89facbe2e3bb0b53d5e26119435cf4c202d618c0d5ce0567cc4c500e197aaf7e377729da23d79d89a9a259f16ce4a44ceaae310962aaa76a397b6a01b5fdf6488cf52246a9f9837c15df34853141bb74b1992fe83a211618dfac428f3fa1792d4e00415a155c2c34cf3c0090a5f85bd212db443714254da131629631e3c5c65ea259ef794909a6b394036088d8122f53b64def2cfe91550a03bb83cbf6e62bccf61fa9a10b6befe70caf2724c082c75728748fd7a917dbcefff18ed5b6c41d0688a416ae3ba8649440371aa99dc6a08c8161a4f617763e09be6e9de4240d862cf8c0cee0ef5c5a2ebf592e3c18bac8136ca7fb275cbd3cc9c22fb7f88e69642af7242f48062fc65a397ef29a541ed391c2ca751f433bb98b5e149dfdbe8bf40fd9012464404eb1d35cddf9bc0d73d30d8a7c95f097ae7aacb67df69297b45fdc966687bd9c721b670669146f1beedda71aea8b0dd47eda6d0aa140dec1dd921052570e59ae106686a58e9bab24847bbcae857f16dfd3c8ce2c502bbac156ff12af19781968d1de0a371a4c555addd5217d7a20b6a4933a82db1e98d758eae3fedb84bc165e95f2f2bbaee4f59fe496b4454200bf3b863154d507ddbf6bcdd271b39e438ff4b90bc309aa45275d5d7a30b994a8c8e91d4edf17ddbb2deaaaf4c73c6f654997aa330080bb0faadc6c406961293512d7f6b05ac501a33ea5c0d12056c6cabd71ea40cd4af2a38fe21e0ed0dbfd586f1c0b6837fa7fdfd42bd487df81496c02ea84708ac3afb4af7e30aeb99656fbcbab801233c8661f8a20a7ef2fc0875e598a3fdfbe6de3b306c3203359a23383e65516c2a466ea5924ec5c51d08045610749ce62c3c42e6e95e36e63f045ef73e9f36b998eb8a649afe4b4d578f711e28a1bf4fe07724a15946cbe813a202653ba4c0b41881aecbf72953b0b79715f59641604ec3caba9bbfef0549f7d28372a488e84fda092af7ad7846c20c8055c244278effb59a7b9730046b013d638c64f8203fe870ca6738eb35d7bc16d834c1260c0700273644e78d1e075f16d275469f1927c46bdecbcf1936106e1b75846d81093c77b72a8665291b17701c4871f8115b9e124230955053745f546f5a552596e2e4ca8f8999dad745396f1f252213b275a18211619f08ad14bd07a3876452a3b9e15a9394964aa4678f4109fa513713f9642a70d9cfa0ce9da3a5d32cbe75b44481fce59124a0faadb3cc021c9ee847875036372cd6ad1f78e993e12d11d4bfb9c998bd5f8c72946c960a1477f4ce60fdb7aca850d59e068e350242c9cfaf8512097c030bb3716aa0af6959852f00a3d9a639dcce675727e6b0133d7eb88a436b5a97da7eb7d639d3e571def152804474854d74a92e0238d84c1857281780c9f2ae789925200850b2e41b6a0c8e704df889b8f2a82c44f87e8f1dd01723adc429ea07fefc3e2c91fed32551ebddd99a58734edac0dec5033c47a2fdcad99560e60d902afacb7010231ef5aef8e379c2e7221c18f834ca41e2c673311c8e7c7f4266e4c51f209360f128c677d19cd6d84500ac572545397d1903ffbf927ddd86ce82b83799df3c3fd9ba38f5fff7ff232cd32be511edccf99a9bbfa0ca3ca1df69a9da05425552dbc20e4e8f349f616f9ade65df43da7787c11651ea409ef7dc43e694a47c8ef8f4b6f5ac5b0a836db7eea061834902a04f941319c82bf7b39c33ab81ff2bf9ead08e9607c6d0d7ed60b772166ce3fd864275e2904dffbdef6b1c86d202aa72a2f2f4238584690ea1332c4ae86095219a3711ec65d724c20948abb0d6a0cd0343a56116deff32b53cb1941220b5f86a9f00adb5b80cf5fca609706178884319d1ad6c7069a1290637700a2fb4de87cec8be3ae2a370b7c2251e0ee8e84e7e7e0a6f4f6ef31e8572779f340b1ec86e9f64992602ec7eff308faa19f2af392bbd29e77e388d07a1b4d130d86838d16128a28e40a810fda4bf9564ca078371970be1b5c0a907f87e86f4663f02b0153bb062ad726bdaf22a052712cbb96fdf1d7c68abe690d9183182e53b634805ed7abd2ac917cedc0fb75770042962eb1e6690d9b8ca7e5ca1897491e45ebd63fbc6e77f5e2e4403c50ac63c0926b8a591669fb9320ca7549371dd6cc491d3d385505f7fed3195440490f0867f54562cb9dd490e1313df508bdfda647b2c3e379318c191a2354c41d779e8e0f4254a92814ae73a3bb5172433f5f93b05edb1285c15fbd4389e9fd98454014acc249b2d721ab81b662ca338a315b26d3d4c81c77bfd824b53151058e7190e7a7aa64af0e1bd127d3cbd23e42c8540cd7c6a3d490c8963d7bc50e0f8eed0696209e4b63671ffd2d7fe5beb7d47bd449ed9479041630426088d57f6f7ce310d37f27107d5c3b8275f1b57bcccc7506cb74b2862adb8f7212c938d479d9035b396cee9c445788d8052164744587c34ceaba510c7814cac47bac8f6cf41e052d10b3d085af97c5481de946d3da61eb402154eafffc3072332761265c764d5173b1dbb9344109b4b451d99d304d33e73ab7f7aba5de01b1d3e885a68a7e0e0713eee537587b9433180079e9566a2da8e9bd52280768f9419776b64b27963d653b09b1006be493ea217a12da615005764dcb4eea9e74cba86352e6495d3ac7524cded5fcec85e4088119a4b1d69afedc2c6134c119caa15470d0b6e59c12acccca74ba0e5f96626e908c17a0c4dd62978bae4b5da677bc781d896ada9a9de7a026591435ec5ecd04ffa20fafe462226322bb67da9b37f1bc2d9b7967030ff203890f30577d6b3e67d0538116257b8320d1f52fe040609fb4e0d27fa73d27f826155accdf5b247d699d516bb38a0de5c269537246bbc7ab6ab3e0f3fc172ccae4852704978be8459228b5da63df1240f04725fcadbad4587e0d50d57dfdf258b18855c38c52ff903ce840bdb7353c1001d53684e594bb6ca22cb8b98d83c3b29748af6b899ebb83a021df6b6e4961a515cb04b35f4414f8d7e3b2a7e35cd3b7f1e062ba267674bf85e04badf8d53c285402f754a76761a798ed7d22d3207c20d6e7217a8ac5d78dcd802b9f81b1d1c320906abc573711bfe6fbfeb612beabce898b9e5b573bf2941829795e46394c475efb93aa7a898bc8072ea972574ebecc9aef501cc44d4de09f4419d0755e47dd0da98eab99b3b81aa9198ec3b119615c93ec9474d07067037996f65e3be2a9c3f6710cfcb956cb4ef7da676dd03f2fb943d8c61c78276e057b75b807f9773822304c2d2e978995f3c19d481e5dd7e1f663409e5e7852e191e8133580a1eb95bf2245beb124431a4ac18faa67d110a71638938ba1dcc34cbcf704e3250e40629af84dd96bcc7f676f491139e4a8ac3598024a86f32294ba2c8c0e2fd66cb774a37abb625f15ebf0e7f2b462e508b1fe3c8eb81abeb0ca3a9a6b3dd4e8c1e6063d81d909859360ece07b16aaac987b5c9a035c2413a864a5f8d5b587f6ad8f97a79aaed4dbc731e8438dcbd1e3bbb49f0db2ba40a27bd2051646f9fdf9048d9a063620234de141d430f6dc14e988be1a69c0376de278e4d05b5fb7fd815a0ee2f263ce57e163d4e3ccb8ff0f36eb410537c435a0166a800eee27ac53da2d5447194e5b61072a3345b83426bd0810dee07dec519d2e73126ecd7f852d279d31506c60d2aa6f2256df1f0448b536dad76707a4ac025616eca74895e1b3f6d77607391c822d432302ade88e0300df29b268b24eb04b2f841dc1942ace20c85f111aa5c1ee33d9ffa54445a4da4e125a792eae694dbcff9b5d4c7ff9fdede0a49e9ce3b49f14f71ccb02b11a091dac445407dedbb32762337fa2a950159e82d8ce4e7226ce208fdafbcab5897304381066c0d8c1f41a2fbbe94d7a8a3a0c7c98d7be722785c7dd4ebd2022f4439a49cb63b10573cd44c4d302b1b146e23b8bb7680ddb515fa367120c19c171ff9af452c21a56710710a0f0b7b1c77e2290183ebfb34e39b07ef5e83fdcd6ec4275bbdf386b7671062c41ffc25968fdc197f72f7241280e3b0ad6abb999b238ec33196375a62f63d0ace784716d299809ea6eaca85643270eda03f37399f161863136a64115ae86d43ad8a00154627184947d3b441d76244073facc999b867d74e4f49b988f05cfff65fb1beda51fe32aa56d241a9afc6af319fd611108832c666b97175ef07e59a82492a7a8123b3d19ac618a93043c492864773894283129579898b6fcc4618b138e660d58010de9378e6a14e595449b83b18771d1c89badab7505a71f2ba2f4e0590c347bc46ad18990aac1530af9fe91c4ca9a078eb56956531d693ae615db3b1c02ce9b338a31dfeb8e1b834ceeb645ba6377184d2b5b65671d555c8354563db872e0a15dfca4049f4ec4990da6a04c80ab485ed92c8eb6bb721ae705ce0a3af1be43685352e40094e576dfd962e8bcbfdb5376e49b7a700ceca025f029c7bb3fe6e1f28185231db8e2f56b9521ada80dacd2c9fa48c7cf2d42270f83d51ea46ff1fbf904d65e126f27f95ce46d17baa9a846531e28eb9f78eaac408727756c33bbb15c9e2a27881717f93bb63aba170a29c8c164afa1c10a3b2e336fd7ed2911e1b061d291fc412d40a9b5094e3eb92dfeaee8babcb1431757320ec4e13f45843904c895ff945d94706a9974daab35a10c6b2428cbb614d9910a7acce4c1e24997a68c305874115e2fe37f3e917e5844825217e3c8b00545cca24ce1b2036328bc97534427fea3db3e9c661ac0432d5955fc0176561ed014d8e4804e1d0565c5fe3cdeccf1e23628815b1446b49fb6717c4971dc70526826d80fbb977bc182b6a0dee1dae8acd08a0bd2f77afd0830b317d1cf3ff59253d72f161d4e9547f81db3f6c464dd137b7544c40c265cd770ca63af777696a287e41fbae73cac046be8d334b5d7a76dbe62cd1f591c42b092437d8e46fc371e2ee2e3b3770d2e90ef6f8d97a77366febd58b649151f8b164a610a4a128be476a2cd6979989caaec3893eb930ab840eee0fa43ba3ef7da9f716adcdb8e4e655777690e00797f6c1b7ff31444d42e279e16162e6ae82fb7146ea8ea9eedf327e12d7370826f8ddd24a2fa6bbc34b1319ca11763ca4efb6dfec0ebaf0c4b51bbe8e921c07f3acbc0c98b37ca6486e532c90bcf435881fe828b01c54844519dd7354971419eeef6a13cf6c5531031c2fdb9df3d361f296502930e2bd3f705406317e7d4a4676aac4e96b8b61d31ca1e24fa301e66cd5a0bc2b6c64d20e82d3df3df11ab4856732afc5ad776ee91eeec44bde4e649a98036db91bbedecc0487282eecc521fdf95bf7d17ff91f8ddc1666dbbb2a0f560f0fb428dc7b27ee22f5dda7eb882cb22b32c1787f8ffc1e59b02d49d9ec26ae2f378be9fb476d6ea47da2145a277605344894d7c260bbef41266f66a834880c7af2ca97340c38db2f9f8be4af4248d52215875c0bf1f25cfc83ebe1684ec184d978b17e075248aea01ab6d44c885ab074b41a3606ff58480c880ba77f4750a0577fec8fbe4846c542e2ec16c18fa2df9d8ecfa5f64a75de476f0da2ebc715d729419f8dc7e1aac475d79381463266a6583fb9579bd266a97d490ca13c5a79d15eddbdc1830096c72da95eac9f20bfba7df425504a558c063a8b139ef3eb6ab322dbcfbf3271fa7cb81b5d45e9495483a37cfb30d9c9733e03d5b0ef688c911da415003ee293e1ccbd6e2f87dbcaab35cde3af8c88dfa3a249c8391a3e66de737caa49d6e6af4e56d4b947f0629e44b735ef67e3c7484483e631651639f38c66e53125dc408adefa0a0001bd34a7da4e4839d7dbe8c1997b11554cfcef084a0895db3d688d705fe75d8ef27b06a6643e27b9c22447d31d6356080f4316ed013d14b399b18a5ac3cfaadc72d9317f3633647824fd171d732042c77ab6ee672087db544b94df01a5b973f13e33af5b7371f1e29354aaefe962eb9be9046465dee751d73c2cf575b99a9f623a6fc811c6ba967fd0ade60b42517d2b51c476eac7ac8736f43f8e62df3d1db58c5f2a3618d6274456ca155b49678a62bed318901cbfee37efb58ae934f0ba098d378658af81fc7b240516280468e1e6d248d4a21536de6d2a91d17e9d49c1cafaa7cd80cc0a4bf12e52c2a876a22ec98980ce8f1efc06ebc07a0d30405b67aa8860ec61d3d041422cfb3912ddd1fa22c87d8e9ec6f75dec6c5b7c4bb792dcc1d5294804ed88d32bf86498358687a0f287bc0f4fd38ab9d27e815200131b08e9a933e4ad442b359881ee3ca6fc5056f5bc87acf1d78c99a73471fbe1b87901747ba36557f8e5508bb32bc2a4bc109f06081cb8ba212ca375d5500919228ff51af03d18377d695c20f43adf8d40239e33c50f6b00f3fe0a8efb5513732a32d566330ea55f1a8aecf1305e019af2781bfbc5397d1d218e3e131d46562793dacf24bfc6b219613e049ddb13cd21b55eaed701dba5b0a8bce0a217b66fc1185da1c9c2a14ae9f815b2f5e7d42f1dc50a6e5549d8647efeb5d88fe779b8d2ed82e603fde40dc6e12a803d0ed0d649a5d2157bc63bf78632d86d092742e035ef52519df781902d5d23c35a4ea0f87bf81b1b5bd46fdd9a33f953bd6cda9e17d3442fac4c3c8b334816dda73518a97f4cc0a82224d52031e7911c2b77743ab2f4a47aac57e8d53e8858b8dab5d22de774fe04dbfb2b13f0cb1865327cdd2e44e5f12f5d0de9ea456b747d1d890ac059510dedbced77f91d65e6a0a6d5dcf2149ef6167e8e2a925ae47baee8ea623ad6087e84f25facba90913879c00f2fac2b888f90b565b9da753e273f8e65ec9cc31820b55e3b5c15ad8578da2a76b5d904512f8734177e433977ea512f11bb4bfb2c8e15ac95d792e8db60965243407388d488d91fe4dbbeadd2b4148b80d04402e3648317eece532851aba3a30b91eb1571d4d34b1481899395842b4db311e95dc629e166170082c37c6c2ed503d323b01363499f980a58e94847d799e6d3568560bcefbce29d7d05622486e312a6f7fb1c6964b14c5d0006403e3c263a7b05bdf3ad01c1fc7ad3a26e41ebebeee20052fad8fcc9069448795d7e2acad891c8bd5bc2ba4cc47d5db80c86747494cf28c372a22ba01d751f69d9d1dd8314bb5e14657626545d5f72c1d9ac47be41ba2f2f942e5b97d9e277f2642a1914425b2c4f55608a8824fc294811dc5baefdc5a16b675550b62db170c2b27e2c585b35edcce41a4cab1cebc0da36cfaaad3bd682ee5eee27e31e89372a28a118a1eeb15ec885d3788ca08d2689bf17311edfafbf24ac1fc35da01ce7a75adc0636b77309dae4f0e8abe450b668ef5a94e4e91de263a9ad0865020573b54b019d01b11f69aba6361221ecda5d2c917225e2653cce005a91904141274c0ec8e523dfd98343de9b78cc98abc9a98d1c40d1bfd6f4dce6bf43de49cd6d4a05fb4f94153b488cc40ba13a1a6fdde73136d416f2c97b3a6275122a26c45521f7e019f614d099d9aae8120525cbdef4f9c8cb1b07182a77653afda4ffef100fa6b03e493bdf12a9ad067c7ac91e1a608adc22befe64689bc8b04e0aeeef0efdf5048d0f78c1d75b70418d0204f8206564681d2accb605d928e9cc64e35901e8d468159a1c2358297bca43a0e87bcddfa24bb205ee9ba1d969a61907397109f5a98648282436eb8e428a170106e9ab059fed2fb74a35ffb0333e72369728fa5e4f5a665cf49ae0da6917c4287fba9f0be9f37e1233974ea677992d4067f4bed80ae974eff9153522a5dfb4273ca5eccab839ab076bfb342b82937749b55fd73ae0eb1245195156d96b5e0e56dd9dee8512b7c3ce1737edfe2b5e8846565675cc8e58b3315bea6edfe811055db0edc212448ed1a8f693eb0cddb47c367e6cad5062822139b5b2f828a690ba65ed9527e29cae5be8b00466d198b650f64f3f66ee63c85d73d6709344f0302dda68950f663e21267a626e40c058e3997d0468ffc688213e6d279479a31fe9767cfaa0d9c71b614ee160b2204afa684ef7fbfa3b3661133aa6842fbd3b7e0c153a30a3dffa101bca2a0eef7277acff38c8f5481b4ba1f1de8dca1622b1ef38101a6c2c762bb03508ac8cfb5b9862d2f2d90c12a7904d07799518dee7f0b1f19a35cd6dd51c4dd0a7e09dfe329b7f5ec0aec23e7fc6ec7f5a707d828b281b26569819313dda9b9ac5e968a192441de3db0ae3af7e8e69c2a3dc920ef83ffbfbfb5baa839be8ccb038d8c6c4efb647b228e9f15644f844db64f6aff20508f19186a90312890fcb18fedf5e16524337e4f76903e9b4df840883115f7d683d01faee51ac40fb81c7d2f711253f718bb7570689c1c629a034218dc59dd9afb295161d752edbb330840b39838fb505190459250d643e33dd2d98cbe81ffd5f8cfb4692ae231a9e5ec296f453ce494e3cf26b839c858b5b50123ccbb3b053613b0ccaae103d29066ba96ef0e5d4e2aa34fe49ee42c670990a56be374b81708eaf1cdc44be353a94516479d7cb992d4b90d5fe0572d295ecd8d65bf3b44fa604b411d369fcc175f5b151dd4b74dc959ee520f82fd9ae085e82ff8e0c4bff2ad956c7cfbc45a21d0dafdfb9a2f4cf1d9a9b95ff0017f426cf5a2bfa95a5cf29ae9e41a945771233c97500b801d0f10f777ffc1ba20bb1d3a8114753f4bcad0f2929c037236ade857ed070f51172d4aaba2c84e03f694f4d015e4a6fcbff1884ada99ed4fdb8d9422558b14352bf0194a822eb0721b169bc751fc6c980da540df49475ccc239a9b714e2133ddad6a9949f16efd07dc2496f27bc8e2d4f06badbf883988edc14026d3ead78a28f49f83b9331640dce5e4a5743e179caaee9d1d8a4c8c7914c3ed5c5982876150e4e8c863d863db3340f75b6aa1bfe4ef7a4076743c2faa0dc1794df981f7243a4d5d2ade6ae6370fac8e2c659c1e2fea15ba957b09ee52da259c901c52efba1bf0ffab454e9f2bfb265312ae4ed3076cfb984a7bed2cd1dda5910293a0da03894c5b2ae25d78d9acbf799987daa366a66efb244fbae87adb48bcd81ef4e26b444be9bc941ce59bcbf1d26029cd67c7f1769bd9c2fb22abd3ec8fd1350719a6f0ddf9691d453cf4420985cf1e320ab6bd5dd4261f421f09406385b233a49145f4c4976718ef7cb886895a7c82310e7cb3a5476677cdc25ba491c2e8044c17d5df59574f69408c20ae835d4cecbd4b425edb46283b1326059118922cb30c7efa8a5a3965f54c4007caff2f756c2de864a7cc82e47886f6dfc3637af66aa5352023f6260598b8932eb060d9d689b42a6bed4766bece8ce21b66edc89a436528c672828d75f1439dcdcf894490ef89f704eddc7f5601594ba8000690ba8d3139b7eeab4b08e7e813fafca32496732b42497dc185efb63ea9310ecc5c7c4a44d38936c040e779f4c7221f74239e9ad46b93a799bdc918b3eddb9da313d9b9f0c71a7a300c4fe9ee45592c617982e118f69679ec2b94481ca6943f4ea61dbbac3565d659c7338e3930db93602cf867ae5487d8d0a3e4e616f2ffca7a8062293d7c97a14f2bb43e3ba4e4195a93cda4f51ca51189d504d60a01cc5ca41a25e833a362dc6f2f5d470ea2b071c71c9a7d81a1ca108b9efc5264e7ef581e14a5be38497dc9f04cef1c1e3c168a5211f3544c32c07084ad8dc535ca167435be7058b9621ff9d5f34795a6bce1d3082801bfdbeeb5f03160c5ecd21d7463112dc952b2620293cd3aeb741fd709121cef8802acfc2938095b6a679c1728acea8b64e96679702a71c54ddeb9a862807b1891dd55de12cfe54dad44b89d8586da7b5c4d198b1d440dd851ee1ada213fd750513fc6e69937337947f856ec391866935e44eac07628d5e8e4336bddba47adacfb05caf695a0f92bd6dda650558338f4dc5eca98abe801db389d09cbdbc58fcb217394a808b3405e4f31c02244862362199b784c3261d1029bbeb35d979fe3d599bccc46a425733d85a4904a73adfb52a233d60cac478f0df6afe02df7698c6ea03b3cdafcb0788de7ec7b0a14f2a067053e576b30b7c331218cb402a5e60ab6b4cdefadf63ea5ccfe2364f7def5150901863b237a056815d81466c27bd050c3963d072bd2ba0f5c9c7750979299e2e513ebba957303a5fb5e9228db4bfd3f1ac053fd3f47654451014b7e91434fcb41082aad008dbcffdb8a7443c25a2a9a74d7f8bbe62ec82f72397253a631550828d0eb71adacb87ea307c67c3000c98afe045c48c92359b6a8dec3aec9fcb9d2dab4a9ba6bf1fed7e732ee8c580fd642d95a0d8a56d5e8384712f83ee29eb4d3789c0b15875c9cbb1f2e1296c695a9fb6063952aa2520d793daa358b1f58d8a5ed55308a33c1a05906be045ebe765dcb74cadb16099d88b1ccf51178ac27519ad97c4786f4ef28ec5709b4b7dc4eb58d363fa447d1bd0e1d2c662967f28263308c274ae28b0fa1340c9ae936a69a152a29a4ffe45f8398f7ace0b9fdf661da1bf994e5400a85f2ed4f4a597d28e2304c710efacf6270277d563be2eaa1d58a4f551f86aba4fb6ac7e1db292d47d029858d2b6c75ee084742cbe168526dcfc36adfdf12b096651ba390737bc8f72efcd87aadc505c0a745ec91f34da9bcffe00421ae6e265d6666d5e77f4b35c5c5a390f6af6e8af660eab7d192a79be9a76b71ca79884d02b6e3f2b969d63df0c3db66251e438794ddf3fe187c0c667a436194448d9785ac758780039a6411f3abafd0aa07a888c22402d00aaad046058ca016dd235b11f1dffa3eeec91886322978019c99bea9b63c039b0c30f361e655b1c523c6c35f2080e7a481a3a4936ef69b57ffd471a4f9d70c702d954879944c37ed18a63a6b66db5682c72a4cd8313daa0bebef77ca764abbbb1851d435f1f092bb2077b13a78262cdd08571723469708d5beda15b4806a923c4c08d6afad57605e8b75eb15969d039c17e1ee4878b30cf39029d875808f9b06ca0c6bd93fd1ff1594a1239cb7c5234077bd1079364ab2b3046b4328d6d4ab4ce31eb0b9495202974716feef87f2b8c9360aab428233af235d7fa9b0cdc35084ff3024403fad2d67242ab0696f23800fa814b20317f706522bce079045dcf06d2a0a31d837e24715133275fb8affe65452b22e34f43c1383d9ccd5c47c539ddee2522c449d1251512ce568e049bf7f75198a20efcc1071cf96d596a7dadad9df40bc2093ca9803cee06620e7dc2528e50a60558bb001651b994a7446f66a385c8f168da5015debc1795d49900714419f48397e5656d13416d0ea8424fba38c94af730e78bc49f0f24716e9bbdbc4518fc4d8f8a32e05c846d2b6886e31b562a1176be4e57d1c332f578933e9b6e7a5085efe66e08cf15fec3881182c0c71ee6af3111c62504c18dd98c79d8d9f2f8530b4d88e5c02049e0eceed3d68426568ccf584e6573c53e95e20d13ad27efc94c414903e1623eb81d1c2aa11c7f0781303aa0d2231540b35a670da2e3d35f23a3606bf2989ae4b66340bf0d41d91a59dc50be39cbbed60db4a8ee0867c262875efa665542813d929a835d85884a6f2249cfa0831c2c1616cc11242bd931e6cfd54bf98b9b28bb707e2ca929f9475a85813ac66e29872f02214799c85781e4b3267a521c6dcd9d4bef1c67104427dc9958ed27aef39d9ac5ba906b54219e4f0dae458c144be2c8ebc068c890b1ae57fbf12323b847ee0598557c9f30b102bd5a2e627e3ba9ef8db07b1b6c58afda4ed44a88dd54937055df2fed3b1d3920c05436c4c0cf505cf406bee8f5a64432906c3c9afe66709c867adeddf2fc6f7e219e30a2947b5ff85e64f1d02f5b2d5a4b68042c40c2bf44ee7e273b48ea8edccb5ca43df02b086c7ff3fcc8f3865047d8b0fdf129c4f6e86d599c630d4eab082850ad7577f911111447043d027cb0fbf95b16c0e83ba3df2834a56e0e8a92fe91ac8c7f90a8644daa90c6b83de5da8e305d2589e6ea46c5d526d2bced0e4a5aad727a3abac364f09c485e9451ae8e3a50dd61ee502ef6431a0110e1045506b11051d1c84b470b4ecadd931deceeb8b12715abeac09eb742bb3728f374be729db1e6d1cc4c33d011bfc1b2730a13393d730649e41e32d3a1624bed7198c09ff3a65d109ba881fdf05c92903094c13ebfe250738938451f44dbe6977c5a3c900db080d2cb105082f049f62e3f35a4e6b2c64c882a384c5cd43745b46534ed1506bf9c226076f0d57bf0460188bc028bae40e88f2d579b89a58427ec9c2936db42c099e147b76557849f525eb209f8dd1cda7a72181dae31b514303826ff3bcb6733b700529d5353ee3accbc4d2804a5d68b650b53638ad93207fe93a246dbafed2751acd06e08983cffad09299b68f2544db98e535de4b5ffbb677a42d432f9b760a41c1982b813c59e2dfbc779812dcb650c2837dcc8a5f6a5afc9f4bfb561bd3514d9a17dbc0d7799821600714b540218a3a18aabc295fcebff48b3fa9e0fc6e1948f298a4039b223aa7ea9e9211b8d5d713bfb761445f000f5fc8954ab70a739000e0fc4b101743c7a2f1d494de5c2f1efb348aeca93b44cbc2b4c49702056057535ad42e9daf1b128afb49cc6e5f6181f9ee99e7358ab537f02a3e3cea384f70c79c7cd4a7df14254fc13136abf9f70457b2339345d686ce22ee8ed2bec1f07acaf9a81431b0af494ea5d2b492a6dd8cba8a271a4e7016b78bcf3be805e25c02e7e281c6f026fa7008ba0de484f68ac7fd2bc6a5d9cf10ad3d73ac1535b665859f854e20c1c9148451db70c276d2457f10a29b0c8e6f1625e10bd88faa0fd17a9fe3ca141c8fd6a223f13da0b1d05dea970d4bd48d96e444c992d322e419617eed1e5ccbe8dcb069eed6874c4e41726e1db06d5be8b6bd7eb0cb22d7df0d6fbd7a0e756328c294d08032690cdd0bbff8a539ef41e1737a441dd3767a94c53b2d87c15ffff930200ea45579aac2619c81024b207690a28b2ca6d2f9cff1da618ef452a99ac3e0740f5e941372323d96f5a11c7ad9bb7b4d91037a00164927f1862c040a9d5a1be8bfd9e4ee938b273e9cced2d8aa12c74a58b069aa9aaf208382f92132ab341af30ae4d86b9d77e8abd76c392a5880764308e71ae13c3721a51b278fa85b81e2de0607bb6e920609e5472936d0562386b2471b72842683c8f89f6e53f5d94b5e62ee81bcb6f51c80f557b91f13177ea77d8a96878dbdd51f301a96334159986301a199e40e994f9f49de40c60b3e97461b666236732df5cb3fea85ebb774bfe18a5509feae56b84e0d16d5c79d6fe6ed33dfe0ca05310eb4f80000dfd22ff4c2cc679a0440ff20dbd9bf856a0c06d94ab59d548e00114d59b8f9696b1b7d7e7ac5be8907873010bc3ab256acf90d30e766c56ea3289da9189435495aa380379836d8b191bf718efd0535f8566b2f88cbe2ae1d60c9e9ffc5016038e69597a44e2a1fe508f28465d629ec22a961d21bf9fff86e23870a633a9b4fbaefcfac4c9214d26758f6d2f11436d7cc7eb0e2602861ae2f1ebee8aed175a9d9c0c09ebf3ae71f2d4b2bbeb2fbf3768905df560bcaaba8ac27ce30d3b971c1b2a2ce2db3122b5558a8348d21f0bd2205a2791bf4158ba96b9a824f17f21605670927eaa4ef8b73a4076135354d78c9e02bd600b5299c89d092919d8535f27be56a8761342c83c631269b033e87a11f3ba85a98300965f151a19ebb5a86fdecc123f882959befa15ff673b46e4a3f12f8c5fa55a47dbeff729dc009cbe80e6166edfeac4086342f6b5c5ac6899607af03f02932cf7b33171cb84383dfb33cf4cb2589288eff7523a658a58540a940c161dcc14bf64156e02ae8eb3482dbadcfc19006a996a94a25287fe3058df1616b83a2fc47aea8a50832d6907eb2bd3d6cd140c825801ff18aad3923314a01c9e3b12fd8d6900c8969982b492f82e5d3bc33f10bfa9c9daa1200ab8b253d03c4f5c8d8cc605ea09050b414171e0de2d65b65fda8096f02be0cd412cf1bcc4c41ba2354d9361c1d62f6f1792adb9a13a6243746f16f2071119ab752bfb7981c088b516b5f8b9fbde0c17a54b0ec2c042392ee704dbade2ad954d6c318b1f792f2b7c2459d23aa70d6fc8c0ad8dad91e8640901e39a39bd1911db8c88587efc20ff4bb08936ddc5e22eac1c4a0145b7ef7257f5d2aea6694769fe3fb6c642d44be9c60b3d715000fc65bb7a6a457ca19c119fdd8de6ccb42e4e196477dfaee1c2037dcb992ebb8f64f1688351ef9596cddeb72458c8e68add8beec0fd8c2e6685bee599842655271bdde9331b3bf79d95dfe262d77714832595ff546e1a7fcc9f0d3744a2a29578bd5e39556ab3f8f9d2da36c5a312b7858070d92e80e7eee4b24d13f92ffd7a5903e2e7eb28b18f96c47babbb6b8a8b615565b2fc5c5c717cb02074be8f765dcee5ca7532f29f181fd7e24203e971af00f5c46dfa97b6f1f633653043c30c1ed5d367a931cf8f358becf58da86ea0cbac13ba5ff5cfa3b1a9666e6128aac74e722109711a428978eb4a6799141609200a5c28f9d9663da5f848cc10ca8e10173732b397439956f513f77a333119ddfb9845dc3c4be7be1d918c328ce81ec81a226c1cd3e33fcf446d183a9ca767f7751b6d9cfd2dba209cf01e8782149511bbd9228fe4577d48463a0ff7e8aff153a33c9ba9786bde24dccf43cb9d53618a006b18d05a71d48d8e78c825c9d162e98f6aa733e6a27be8a0528f9e368ecddf45f38dce76c21dbeba191154a3e966dd98f7773702b948c723d086e77cfe821b9f743867133","isRememberEnabled":true,"rememberDurationInDays":0,"staticryptSaltUniqueVariableName":"e58622878c5b4107a5c053c29b821537"};
        const templateConfig = {
            rememberExpirationKey: "staticrypt_expiration",
            rememberPassphraseKey: "staticrypt_passphrase",
            replaceHtmlCallback: null,
            clearLocalStorageCallback: null,
        };
        const staticrypt = staticryptInitiator.init(staticryptConfig, templateConfig);
        window.onload = async function() {
            const { isSuccessful } = await staticrypt.handleDecryptOnLoad();
            if (!isSuccessful) {
                document.getElementById("staticrypt_loading").classList.add("hidden");
                document.getElementById("staticrypt_content").classList.remove("hidden");
                document.getElementById("staticrypt-password").focus();
            }
        };
        document.getElementById("staticrypt-form").addEventListener("submit", async function(e) {
            e.preventDefault();
            const password = document.getElementById("staticrypt-password").value;
            const isRememberChecked = document.getElementById("staticrypt-remember").checked;
            const { isSuccessful } = await staticrypt.handleDecryptionOfPage(password, isRememberChecked);
            if (!isSuccessful) alert("Incorrect password");
        });
    </script>
</body>
</html>
