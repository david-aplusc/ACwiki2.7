<!DOCTYPE html>
<html class="staticrypt-html">
<head>
    <meta charset="utf-8" />
    <title>A+C Animation Studios Wiki</title>
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <link href="https://fonts.googleapis.com/css2?family=League+Spartan:wght@900&family=Roboto:wght@500&display=swap" rel="stylesheet">
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }

        :root {
            --yellow:  #FFE000;
            --white:   #FFFFFF;
            --magenta: #FF2D78;
            --black:   #000000;
        }

        html.staticrypt-html { height: 100%; }

        body.staticrypt-body {
            height: 100vh;
            margin: 0;
            background: var(--black);
            color: var(--white);
            font-family: 'Roboto', sans-serif;
            font-weight: 500;
            display: flex;
            overflow: hidden;
        }

        .staticrypt-form {
            display: flex;
            width: 100vw;
            min-height: 100vh;
        }

        /* Left: Typography slide */
        .slide-left {
            flex: 1;
            display: flex;
            flex-direction: column;
            justify-content: center;
            padding: 8vw 6vw 8vw 10vw;
        }

        .headline {
            display: flex;
            flex-direction: column;
            line-height: 0.88;
            margin-bottom: 6vh;
        }

        .headline .line {
            font-family: 'League Spartan', Impact, sans-serif;
            font-weight: 900;
            font-size: clamp(3.5rem, 11vw, 13rem);
            text-transform: uppercase;
            letter-spacing: -0.02em;
            display: block;
        }

        .headline .line.yellow { color: var(--yellow); }
        .headline .line.white  { color: var(--white); }

        /* Login form */
        .login-area { max-width: 400px; }

        .form-eyebrow {
            font-family: 'Roboto', sans-serif;
            font-weight: 500;
            font-size: 0.65rem;
            letter-spacing: 0.25em;
            text-transform: uppercase;
            color: var(--magenta);
            margin-bottom: 1.2rem;
        }

        .staticrypt-password-container { margin-bottom: 1rem; }

        .staticrypt-password-container input[type="password"] {
            width: 100%;
            padding: 0.9rem 1.1rem;
            background: transparent;
            border: 1px solid rgba(255, 255, 255, 0.25);
            color: var(--white);
            font-family: 'Roboto', sans-serif;
            font-size: 1rem;
            font-weight: 500;
            outline: none;
            transition: border-color 0.2s;
        }

        .staticrypt-password-container input[type="password"]:focus {
            border-color: var(--yellow);
        }

        .staticrypt-password-container input[type="password"]::placeholder {
            color: rgba(255, 255, 255, 0.25);
        }

        .remember-row {
            display: flex;
            align-items: center;
            gap: 0.6rem;
            margin-bottom: 1.5rem;
            font-size: 0.72rem;
            letter-spacing: 0.1em;
            text-transform: uppercase;
            color: rgba(255, 255, 255, 0.4);
            cursor: pointer;
        }

        .remember-row input[type="checkbox"] {
            accent-color: var(--yellow);
            width: 13px;
            height: 13px;
            flex-shrink: 0;
        }

        .staticrypt-decrypt-button {
            background: var(--yellow);
            color: var(--black);
            border: none;
            padding: 0.9rem 2.8rem;
            font-family: 'League Spartan', Impact, sans-serif;
            font-weight: 900;
            font-size: 0.8rem;
            letter-spacing: 0.18em;
            text-transform: uppercase;
            cursor: pointer;
            transition: opacity 0.15s;
        }

        .staticrypt-decrypt-button:hover { opacity: 0.8; }

        /* Right: Vertical accent */
        .slide-right {
            width: 52px;
            flex-shrink: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            position: relative;
        }

        .accent-line {
            position: absolute;
            top: 0;
            bottom: 0;
            left: 50%;
            width: 1px;
            background: var(--magenta);
            transform: translateX(-50%);
        }

        .accent-text {
            writing-mode: vertical-rl;
            transform: rotate(180deg);
            font-family: 'Roboto', sans-serif;
            font-weight: 500;
            font-size: 0.6rem;
            letter-spacing: 0.22em;
            text-transform: uppercase;
            color: var(--magenta);
            position: relative;
            z-index: 1;
            background: var(--black);
            padding: 1.5rem 0;
        }

        /* Spinner */
        .staticrypt-spinner-container {
            position: fixed;
            inset: 0;
            display: flex;
            align-items: center;
            justify-content: center;
            background: var(--black);
            z-index: 99;
        }

        .staticrypt-spinner {
            width: 2.5rem;
            height: 2.5rem;
            border: 0.3em solid var(--yellow);
            border-right-color: transparent;
            border-radius: 50%;
            animation: spin 0.7s linear infinite;
        }

        @keyframes spin { to { transform: rotate(360deg); } }

        .hidden { display: none !important; }

        @media (max-width: 600px) {
            .headline .line { font-size: clamp(3rem, 18vw, 6rem); }
            .slide-right { width: 36px; }
            .accent-text { font-size: 0.5rem; }
        }
    </style>
</head>
<body class="staticrypt-body">
    <div id="staticrypt_loading" class="staticrypt-spinner-container hidden">
        <div class="staticrypt-spinner"></div>
    </div>
    <div id="staticrypt_content" class="staticrypt-form">
        <div class="slide-left">
            <svg style="width:clamp(60px,7vw,90px);height:auto;margin-bottom:2rem;display:block;" viewBox="0 0 160 160" xmlns="http://www.w3.org/2000/svg">
                <circle cx="80" cy="80" r="80" fill="#ffd411"/>
                <path d="M139.5,58.6c1.7,7-2.3,13.2-8.8,13.2s-8.9-5.3-7.2-11.9c1.5-6,0-12.8-8.2-12.8s-13.3,7.7-13.3,17.2c0,16.1,9.2,24.1,20.6,24.1s11.6-3.1,13.9-6c.3-.4.7-.6,1.2-.6,1,0,2,1,1.4,3.2-1.6,5.5-7.1,12.8-22.2,12.8s-31.1-10.7-31.1-27c0-16.1,12.3-27,29.6-27s22,5.8,24.2,14.8"/>
                <path d="M49.5,82h-19l-1.4,3.6c-.8,2.1.3,3.2,4.9,6.3,2.6,1.7,3.8,2.4,3.8,3.6s-.7,1.8-3.3,1.8h-17.3c-2.6,0-3.3-.7-3.3-1.7s1.3-2,4.8-4.8c3.9-3.1,6-3.7,6.6-5.3l12.2-31.7c-1.6-1.4-7.2-6.4-7.2-8.3s.7-1.8,3.3-1.8h13.2c4.2,0,4.8.5,6.8,5.5l19.7,51c5.4,13.9,8.1,19,14.5,19s6.5-3,3.3-7.4c-3.4-4.9-.4-11.3,6-11.3s10.2,5.8,8.1,12.4c-2,6.1-6.7,9.4-18,9.4s-23.1-2.5-28-15.3l-9.7-25.1ZM31.9,78.6h16.4l-8.1-21.2-8.2,21.2Z"/>
                <path d="M84.4,79.8c0-.5-.3-1-.6-1.3s-.9-.5-1.3-.5h-4v-4c0-.5-.2-1-.5-1.3s-.8-.6-1.4-.6h-.1c-1,.1-1.8,1-1.7,2v4h-3.9s0,0,0,0c-1,0-1.9.8-1.9,1.8h0c0,0,0,.2,0,.2,0,.5.3.9.7,1.3.4.3.9.5,1.3.4h4v4c0,1,.8,1.9,1.8,1.9h0s.2,0,.2,0c1-.1,1.7-1,1.6-2v-3.9h3.9c1.1,0,2-.7,2-1.8h0Z"/>
            </svg>
            <div class="headline">
                <span class="line yellow">ANIMATION</span>
                <span class="line white">STUDIOS</span>
                <span class="line white">WIKI</span>
            </div>
            <div class="login-area">
                <p class="form-eyebrow">Studio Access</p>
                <form id="staticrypt-form">
                    <div class="staticrypt-password-container">
                        <input id="staticrypt-password" type="password" placeholder="Enter password" autofocus />
                    </div>
                    <label class="remember-row">
                        <input id="staticrypt-remember" type="checkbox" checked />
                        Remember me
                    </label>
                    <button type="submit" class="staticrypt-decrypt-button">Unlock</button>
                </form>
            </div>
        </div>
        <div class="slide-right">
            <div class="accent-line"></div>
            <span class="accent-text">A+C Animation Studios — Internal Wiki</span>
        </div>
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

        
        const staticryptConfig = {"staticryptEncryptedMsgUniqueVariableName":"940c02031f69d24367843cece0c60bb34087f39247d4160d1b6866471bbe74ebd0952a3a8e2cf5c034d14c081782f85d447c990078f0997fd139a42f81bc92597919d1e8b30ceb21fa0d6f5ab540b982a81243d2e374635dc33a6f56900da9a25b8601d47a452664e6006a1ecc7315a4f1f169616c3181b816b171984c203d7d7e40aad6c7c8041b855131b348e3337d3fb8574499938a8bbba78d5e0cea72e5d9fe235380ca34097296fa967f1f99a9652d11c774ae114c52593c71179bbe217662dc559bbac9f74e831fb75abbb29cca94fff27e79ae50afc4cbd21649d45a636dae1575c5bbbe015b6567fe8604195a8224f7dd375811ba392e4521cc7d3aa0ca18ba755bb63c012d693166b7d7f923abed3b7e7dd128a64eb984527fce6b72f59dd3f9739f66a16a0ddddbde4b29b7095546336412d6b224e6c78b0998d59627878df858e384fbc52877303bac5c19c103cffaa9546b5b0853e8a35e10f9d2a1fa8a6266417dcf8d4bc6405c7a497dea2da29fdb9eb46b7e327f1bc10ee3a219d060bdc4494edddebcbde01fb12b676f2ed908932037e10be81f088fc4d521343d7e1ed8f6ae212e2982171370de34b79179d49e53c4dc8f1204e839b1c4d2877549b1b224298a676a29e863bf3b84ebb467f3689c06ff3988cccce2ad2437a71020cfe843c07772d397643b105290e3428d1bdeff708da408ac10e23c956d82bde7b29bb8c06781cd543ee7d58b41a08f6ca619f687e8177a143b14f44a5f127cb89995b4a71a7abd2c138d6dab99b41788bef90531f1b1b7d11148276c9180e242578cc6e575e6cc4f80656bbb0b78bb0652511613fe33d74dda7d0d925035a744265710a0cb6aeaa8aa7ad231419a68d0420e42228b65dbc5d0c71d1bd8be656f1ebdca2db9294d9aeae328807ad6f65b528cf6ec8368e13a8a3ff053b2122390c799748823ec4ec92d4b997c14babaa8b077dc8ea26d7e335eb495cf2eb7060a1e57d599db6b2eff3361c9f08acf0060f37f21cd991c3ebee0dc9c9af0c2c9df25469244a31948c241b50886239c3184f807ce0a7ecb3f68f0c7c4c99c26248f65efbfb1f6b5f41745b63c4d0ed6b052a0216c64a1629b645cd84d27423edf206ecad7e036de92d505e1a2598262bd7a5d899fe6c501e9e31c4672480c4913dc27f24e7539dc6863a708bd525f3eb70c3e82069bc20c7e2b33217081cee5673b0f44899e9c7145a1a7e74b253b9c5b011cb25a518083ef962cc2a3458b0d49553daa59be5dd86475665340926238baa94f2429f3ffbb04f322fe2c93baccff1e5bd34f75465ad67c4d9c0515f73175d82d297b1214d10be3636b19d20c40b472e4d57f8dbf59bdf61d82c11c436f0b89c1dce5dc38ac5bb1521db1c25b6d4bda387c8800926f48d9b01f750c63af3134d6ed4ed1e2012d0bd5c2591567e4ca2a27388d3dc44b7eec370e9ec6b70cf4ed4907905056f2c80cd41279e3212c50444f889f99af9bb1a35798faecc70c3873729afde769130699bc0efccb03044ec1ec232b0e337f543639865879ac70e7b546b903b801528c987956ae057b316c60b8dc4d00ee837131d2b02a07f6522a1e6dc1f0d5a47461d530ebd0817d185be4f32272622c33354bcb4168cbd69ca88df308d58105a09b4855e5d595ef26c2e354eea57c8ba6c504e0d98035d9c2bc26d79635172a14e5ec3af4e9144e3aa8fcf45bc0a42f679a0d1245c66fcd618c443af46a4933199b18d9aad93fb000d8930a28a49b1ff443f34377a9dabe92ad88ba78ca7caee336985b33ed310241cc285cfe6f15ea05b8ff82e1e7b42556e86253b32b8154cf8e6d92d2675b560f4206a7ba07998f1a8a3e4d81bcc465a3b5f16728ba76b36ed31cca84d8c90274bb283723398786c5fa0d183078c6dd51afc4e27639e30c9ff55096926ccb08ef949915fb06ee47e62975d5b0721fefb3fd2b1bc06b0493a46882af0eeab85e011ec52390a47827054d5efd4e87d26ec34fc0648e00cd4e2e83b8e506fc0ba67cd75f93b12ae6a74dda26eb011abcfd423c05c0fa1c31bac5b37283869f72bc58d6c3b8cafdacaa124cf0b73ccfa49b102d9db535c55f4a03c83658afb939d4dfddc43145e69f999c86c9d2eb302a4ced814143c44990d39ce0e169f80b9e8363ce3f2e799e830416ffe5f0bb015da9708801626c0c600e905a0d56a0d6f65f7dc833dacfff2495f6f4dfd2ba3548b14fe655df62c6ab97fb40194c4bb70f0c57210a7b6ee7982bb25d4da8e270b8b88bd33405096dc35ea092f6c64698d4d3a78456561b6b6da91c428f0065c3b92c6f79a18241cc4f475a581612aa50774a3ab29994312793f2f8b03e21d3c9224500a05908c8b6b376ae6c5596cbe8477096a944d2074a02f309ae828773ddb757b30fa6b333c6a8601c737cc47d10e44b30db476737a0443096cea140373810e802525b91936b1befd9ce8669f2cf4238ff3cc52363d2a3a1363ed406639481370e03766dd5bbfdedca1e03126a10c5ec2cf1c174d08cdcac809a50c15c494ba84f00bf6d6fc21a87a5f3040d28c7f528b39ee4c1aa03e27bc6415195cc635c2e0248fb4958a10b8d5da92598de8f0f09c9745c2bf11c0b063c83862d98ced09789455e84c8da30d2ce3c9114715d557a397612f649a84496658fedaa615e233320bef9b97098189508d14388990cce6acd54bdfdac7c22f36840d614d53b97f7b741db4ddc7362d3d0a027e006653d8bc19217b84fc178f827ffa446c92f0c9f88495e1fe7a1a9dac956000d8b755aaf95907ebf59cc01165bbaaaf4148f8c13c04ea102359ebba4005bfce8dbab5c37bde7f02c922cc4596a17db0a01cca2d1a460cd2af6622326fc827d6d3f64ca286ece39b315c38ee1ba8d933bf8e123429aa3580dcb67631a39d30b0b05b40674f1b1113293f664a9651f136dd3cde47b8e55b56cfd89a7b0efa89c04adbdf71356bbb6a63344d022e0ea01207628a07f6b4686a72c84c666ae7015732fb3cc1db32189863b567b8a8f0d0a20733ca7a6f7efb85272305aede69efde5693e6cc6a286cf509b56ce7cffcfc4359d7d14f108f8c55780492a259c67b91b659cf435cbc130a6fcc411e4a5dd79ec5a119c0dd968d6c24ae8bb0369503d47815c5d467afe550c197f63dd8e0349f8edadf4f5c3b3903407aa509807a1c5ce1976dad820278252d7a26ee979fbc879db41f8da220d87278db801efd5239c262a154866e298b7a3bfd3f68c78513e1d804ec1bd716c9977146793b0dbe76330dde9e6623761367727594fd12c6d28bfa2ff741442afefca26d74685df73a0cd38dcdaa9b0a4555ee5b463863b02570a94ea007bedbe7cb0b9aa78e605a5cd4c784ff4d57ab68ca23f6409ae577d7dd4dfe45ff93d84631dd45fca806f5a573a07e2664375d6a35345ba5579cf6a9c3bf5a743c7f1a592c395ead4d77df5fe9ee9731cd36ea2bf4bcee06964ad554ca361e2ea71df80efcbcdee2e3e39f0c8d5d644c292408742d99aceae1f06a539619ad5b78d82cbacfb9295946afc04459d4994203e5aa54b96f3d8020c04a97a6172c3c5722894efe58dbaaea29e211636f45dd1f17817b0ac3076646d5da250e92d4b36a0f2eaf6e21487efb919c6db45112c77d3fbabadff54bdd1041d762df853e9c8d027eb8f0d9e73d200afe3a7d4e308e4a3384529faba7c17f36115c04df0ede360cdadcb041e461b4f61ad028aa315b2bb585916ec3e5f0f2afde3ad35e2ee9252d7d8941d638635ff64b140c5538f6c7d2a5f7978a94b4650d135fb6180baecad32112de62d51a90c1b976589c3f36e6e1e9a1642b7ec59d840c2366f5c66e6bb52d005d73c51f64209245b0133f23a2e5d30dc0a28e0acf2b5c796d46fd1098d73ad0c33ce6f4de82e53a7e0d167200ac748a1d2c4123447be3135ae4f90dddcb5b13695df713994c16de703e9ce085b044c5e6152446ce48fc19e44afcb1854ee0f501c85a671529bc90db23845251d0c3f8073dafb647de79c68a28c3eb3b101242a2d0298b29d614c13237bc5b85e79c633a904b77cf59af9d73f881d5b59941eefcb845f4b6f4e845bf311383b1ca1f36a00e8b56bc69ab469b52da2584490353d8e0fd6e6267e08476beb29aae30cde02b6d2f5190d3193a13f0ec5e5f0356f07a453bab1bd7646539aee628fd013a6b83ffa23ddcdf810bee782fca1cdbb81276bcc456913cf8829316f8d6a53778f80cee1d4cdb0dc0f0771e4334de568dc034a488ebc914002263f4dad32f7b7503a1f0168096afafcbfe60b8a071ae992275c7f01c32d534eb15bf6384172a57cb5d3450016bcf494458ebac1ee614366d466b05ab0ea47ae3f254c61969a4d77f9a877cb487a11f634b0efe1ed1fd1fd95409a62ee5d5610fb20800d92acd269641c10508b4895b44b3f310a1d002deadac2f96c24dcd5a6520ad8a4413ed052acdcd2c0d54376f17b47b06bf96030d1be829e21fb5b4f1cc78de2cb92e2f55b02fc412d611c326d9ccf871812513c0ff468ea4ef2893b4b91393010f44304a092def1c12d84bd44be927b124106b6a2f0cd7c157cd349b6e6096af296f0c60c1a11093f825cc873758a228a8249145795239bd8e12d3aea6ff87a7e3e8ab4634004be53580d3b7ff27e86b56b48cfe0d368f259a3ff2686b6d5b7b151cce05a9d4b6cc4dd21a20d27602a7105f24bc410975d37f4570f61919d879fd8c5ecb83ebe55b5f56f5debb08d5526eaf2ea6fe74cf94b2d4f0306f11879777ca3262004383804cdb199d7ee5b48d07af2c28a807323fb5c64de1ba8186433c297885daeef54dcbd8de8010c8713abcd2997ed136c42bf29193171e8d6c800f62471b4ac31739684676dfa6618cc8404507e8273c0e661f9b6503e8ac549aecac0a1d60cf24ea9ab8e070828d16e4ab25cfaadeeb3f4fd8f182340466c4a5b7ffcebeb57bed28771b9327f6bc78a7491190c68773f1791b6cd0dfa0f04b9dc2b916f9a0591b5f9db6c352bf5fc9d179406de18e64fdf4ca532e36ef5c4b56ebcc6f8c4bef819fcb838ea79d218ec9bd7e58d1995cd705c01fe451283cd8672bfe34caa3f018abac61dd39794af70d1d7016cc57c11875d1f4c056030419288471980ef91bb25142fb61ba67dc83153eb9c999b282850bf3a8b06cd9107fcc726465da62aebf9eb439110b0d57b252980f08736c2b825673502b94e2bfd65272aee638cc3c255028becf95fa883990b83af2f78b76faaa8a1f852e8bac29ac07aff573c9bfd8ed2504b24f31eaa15a5693bd5bfe2021b36cd8c8500ed30d63d8c982630f6c9289a92f5e73dd7409f06c4566cc86ff27b6f369082459e8a24e81515226d43b844abfbcb44c9f47531031d18456254334616535710296c8eb2504e9f641e8e083e67ac9c3d7c8a6780815ff5c7312fb7f12668d858e02ad4e9d82ddb8c29b95fa487301fc81bc07b2f1b16e3c200581ccba6ec20965403d23a317ec31f086666ee8fc1423d5dc0c6dffe37cb71d5bf375fa0ddb81ca7139cdeebe823a5e8e406534d44680897e49ee3e2f968c11e77f5cbd0b2a9944d65f709f604ab880400d93fe201cfd4e785a9ffe80156f18f0c217510c43304365b72d7a4eb1c9d75c556d98692412fcca020497f4c08aa938289a173bf302e6e9390abdf6cdb7f363717eee3f89ad42e0268e75f624e9650efe066770239721e6df377a386e4b4912c72c6d4a0a32410b8c539b39b024b57462d9fb134818429566f7f4286bf4b563f85f9af6f93b056f4d3fc8a0fc53ebe9ef87dd2dc199d4812bd49a6bb791b7d166a13341e2e3b33522ad8a5bbded99a3f5a480e93d8cc552093661298f32324f3857bf8535344b2abf0b820029262a7349d74227460535e340731d5e3f3e0edfa44bbfddcfc92ff6cc9e9526f0e79a3c79cc33dc52599a768c46dfd107d86185314d8a3302008bb5f5f6e6cddab89a02981b2d1a2704e9cc774da499c779d955f1594207a79caf3c3be42c38963f2de128583f40a008e5ad4ccaa227b55fecb109c533a217f7ac4051d4d44b1923cc007a34ddcc75f34d12bfa8080ab4365b887680329029e716db55363c340fa4248809459aa5e96185256b13326b320b5f44f0716c193682f3d08b6cb1aadaa93df933c12625c91e6b4ce354092c516af05d6e424267c923c2998f6971f37306466043652aeb96d555c1c0ff2e5a860b3190a45899adf2762a9f1aa762436a07713fbd04a72f95d4cbe67304169c7140b11a8e21db4f5353ba37c615490c3d63febab7eb55d4c265d31c282470996ca78c3e8ba782af7f4abd5c0e64b6994fde36913cd4fe9daa6c7d0d329492f532b2e171c5a53e38cb32b99733c28fc8fa4c96fb80b96edbd4a7b2de58c1f4be8fe23ce73445c55a436d48ce32627e329c3ac323be1e1228ae35581bc0d54c302c0a5735cf61cc5bf78efb4b85906a420bebe08afb3fb69c6b0dec05ae9721eea6758769607ff1df1d4cb946b8f738c1e0aded7640d1429d945eafe697a53c117413bc069ca0d830b9fb2b128fe6b8fff019228be409df1e5db8df05d61017aa4eac83b0a8e104c750935cf53f0d36e835a08d288fef7666a8c4d7921f70c64e3a9f2a4d1a4ef4e504e3685ecdb2f2844746c9510e8d35cccf851065b4651aadab0dfabff2bcde3f790488b98a9c0d3340147bd443c082cbf0f74b50d35474842a62258b2dd84fdf382bd2d463e5b9ae08566ef8c0c82b633ac31c8f8397e8b0537997ac85e21da45b80e3257e7e0162313e0ac2434f659df35daaa26fa20ebab9701eea77bb69e0c67a9268a1a0996c7e2a9fc869c0a399d368c77b16aa02aace78f302b51f5ef7f5a8c39af7df210ce35ba749b23e223b61e1d1ac2e738e7658460d6e9aaf71d2fbb130c351e9c828d13a8a9b4ab54250d10fd56937bbfc3d7e4f54445e08210195dc35cb049d9be7061c7cc38a9cb1a8c06a704ce90bf9e5d79b874505085276ff02b341e4881da3e0721fe9b191b23dca654fed51401c49b5ca5cb52b8e9941d28b1630e1c88f987dade9248296f69207559544d28c4fd02b67239c17e0f84aa455a5d8f55da1138cb29d5c56c3a33427d8a4d3b69b70cf521a2108c0a3fff90e7c0e274a359f5b526a5587a054f637c85aa6100595392e92168946d73871a82cde91674f48985917304a709067028863bae71ac33bd3db6408b2f51d3fab601fec6df5e4b9cb1089a1ade6eb1ac293db05d23b2249634237e41178c217353262860c869341a309b2b6466ded5aaa6c2e966811d5ea00c394a542a3e08464615eecc225d013e9856aeb32f254e68bf771419c579cd41f684b70f600f134631c44bdc636e3f4dd82a8051fdb3838bbae4a00de165b7322c2d76cbc80388bd5208f9539a7a187aa40555b7e101419c40914e5de92325536f84ccff6fb39dd42afe454dff3a467cc35c929d330de62b4a4be8ad6e6adb6c10ffee74dba9789d2d396d11800341738ad97b68365d188548c68d66f0fd8998955d402f5134dc14eed0a5dfc282991d20572339e6715382eff0a54ba79000099a8fae31ea3f786e8b4cf7f4fdcbd7a5598ff3fa7879c46041ac49d904a15670924987831bf066d287fa19cc10858d3d71a9a04792099ebf5faffeb0e1a4d6ecc8f40c754c5f9d4b0e47292f371eb6392d7a22d04c2d0e563415bcd07a8bf505d3a2ec42dbafe36ff8596f30a7301b1ac0ac35f1506f286039e3944daa41a018b8ab6f416e0b74d66266bc0d44b330ef786b3fd81c375bd2873949fd436a02be5d9b384ddda9c1936cf49e36bcfccc1000b7dd08eb3aebfc55d9bf33ef8d00f3c33a8ac2ab4b9440a314ce4241ca545748011145a3772d6a2e899623de0de7a9cc78fff884ce82c9e776cbfd7144cb8cbe2c7be29c1322f613601f9a446e46c90be72ffecbac760148966a735eafea6d225724b076e54da268a21a54ac8dbc317c606aece3404fba00c5b66fafe9930b46ec38a0c92b219452986302c8693bf84929fa221b19e62ff1272d1dea85f198aa26557bb0802b182248170ddd4d913346f6d110b589741e700fc5bd40458ea08f154e21a1e9969892b62bb92e2febcc0e8398e1cee75315341b44daed472f4b744bf677af57ff56713d61259818c1be5f5ce41e31530b8503f7c844d6f734227edd0139b9312ce7a62ce9d6d619eff0cb5bfe78c73a04705146c4fdebcbeeabff506222e134ac141f09243de3b3b7841b25470e3cc644af8048bc58b421354bff91beb64c566b6356a197149dd6187ae55e36197d699f7e4e45480dc361f466fa99a9d80fe27c2827a67d4d28a469e2ee234bd56764a17be534b1f921c5d1489ad954a8c5491fde5fc3f95706a19974b64e0881a05b4164359869b7406e59c85ab3f0578f97923a54fb5dcdd7879b6e42de4a89988e06cfed4f9e9157b151942862e5d85d324cd61728ca158e11fecf06bac14ea3ffba69392b8d40c93ae787f826b0c3f649e15876fce579d4b3e703901326b972b53bd1c5af94891c1874b59c6bf9ac45271275fc84a568790086375c10bdcea8c733d02eed5213fad66433881867c4cfce81f6a26e0502bc031168c6d7445e57e2463d711d6defb6f2d6407485df04d2cefc65f3acf6c2027b9079b2962a105b0e95418b270bb813ae8b9a631968fa99f63aa077731dbe4354782f81aca7ed34dd020cd425718a7a875bca4da55168f5c5b1c219f2febb62b8cf31bcf6b2fc22880be5b3bad79e80ee61972dc67c994754c660a5ba827a00a44a612a999e78af217f1b78100cdba09a8420afcdfa5fcc340817942ad0c518d063e470a6dc4f32b013ac11a8cf698a4afc7504e0200ed8fddbd005491e8fae41a0a6bb8d068a85bb009a0bf1247882d13be9516c2cc38b060922caa59eba8a51f6a35370a225cf74dfceb8ae12a350145c3baba7b5523fd42c1754d3b4ec458b24212d1c786b7bedac20b5a8389b7a916d330c5dc6f39d63626b7ac26cc7f8db68bb374aabcc720220a3d01b2ffb4e22aded9509086eb464368745564f489701a91d7282e08d1db23b146f6c18005aa1b7c9a0911311b4e2a26199d5a69d3a00d3954449b226ea98648e9bb64bc6e783b4760321bae20f79ed80fa23c05abc4f3e21167b5ce038bfd4dedd17d96ce4e99b24a42d4f2141ef147b866fcaf536061b40a7ae641ec9d04cae7fcde23a85330d18b3d8c3b0fae2d4bed94073e3750b9408c21aa79c61dec0d2378d20023236fa8327c3eec1ba352c00794ca3b6f2647810082324a3090b912734701e7559209a826eb68e446779794bb08e32c7f25af41a125ca733d738c4c4f81b9a367429701dc04b95a77c9871a53dc5cfda6635c9345c57feda960c81b96435215103b0be3ae0c27499bf3b3582fa26fc7ba6ea250277e9d7f0de67ef80050bd3e4f6654c8f553328f9c2c6d288448f2e24e78f188612a05f1c20c386cf5364800165daf3c058eb09c46207c4d4f744d7cd2ee14e7dde14b28158ca2d12fe79d54fad87251c7a4d0ec444afd917c7a0b89feb3d3ef3f1860a9ec8eab83b7436781071084c5ac099724829208a32eef4f4db7cb29280b3aeb33be5a5996089d03cfc28ed1abe12d958ac83b35994e3b32f7b2d5948dbe101e0d25d67626070ff14ae6f152766e839698d4c772e2abc8325a3b8f6cce8efacd88ebd657ba9436c88b932a3a187da346784ad45df475417daf5d5805f4e6d2099d23b541f36a7e16f203efbdc9a119437994de1e334d1dd2fac10a5022cd617d135378cace93c22f3df1925343c2cc6f5934edd18639c199daa8f3a6641d05841e23e7324624cd30b59a8c6bec503d9fad787199d52327c4ff29a5850ec17a3a8ccedc357c8c59e5853c683ff3459b53733fe8314434b60bc44534da68363cfd26129e7e81933a8c2b1c8e712d8fa1ec6c47da83917a616465c36d87963093b1df90af7c37d26787d904b51adabcb03580ef29618199d2b921eb4cb897ae720da01b457cd280aa7184a8a394ce3687b1d3a3ea1301116e9b23d90197be0eb1611ef38c3a667314999293a234c3dd175cf0d2e348df79089f5f4ffc135c4e078a5aa7fed4268c43dbb307d51b15e0389f15c5537799480082fdee85c482ea2786d0ad54b8c375504172212d01bfe4cbd8fd35d8c662cfff23d5fcc9b29eba63f235e9577676e019f214dc4b332ef9fa52647d55ffa6f787cde408d09e8e8362d5396409e8c2097534259f456256986d451b14c274dac9e13a7d982a55f4a0f4d088bd6fc8489b0d670b0a51109ec971dfc52f2f7972fea567ec4b25643c86bc95a3690d938cc2b2c5d6c98d285bd09f4eaf3056a3db96bbbc627f55506b7387a7ebfaf5cab9cc3fc924673ca267a15017c0617359ccac06a686e98b22a3b30666ae04bbbd2a7e8acbc5df39c118e57c19026695f196283863ef8ef983ecf2f758fe5f0e655128cde5c506b87b7f93fce1ebdb97cb5261cbe5cda4254e1c4335652a12350af4ec9d69bba4bd6af7176a6a71911976f019afb959335e3d1839b3d6e6a1d0c9e7ed94fc7282b07d5c7969a230a62d610e619d1bfb3a49edb26a0d30f671feb548c0bbfb0abe4b5db3c48605aa5bab137843f9242e5dead7c2e9b7d3995afe36da3520c6173d4316d5c6777c991ace0b8d250833295fcc93b1482ab50b074b644f8aec30680d79792dd1096802945183e1a99edc569755e86d7e960e8883d03f4ca64739260fb691d97cdf9329ae77f053521824be931660d319ceeb6fb47e4cb2f105005f3ed92d0f3ff393b5ab3c5f0407f4e7282b25dba7be0d64b4684d93f142a17b2d49dd93ff22502ad697d7a861b5181dede38ef158578506bd97da71f7e109bf7b4ba87c8545149ea9a227ec8591938bc798b78f7a6d90158963f26a479afbc9cc4fda96a459cd4d3258a66981b1c255e058939a1814a7e265a8f4a7b375753381df9819a08eb6e0b240a6c176dd5c606072104ae6a61297e0a07f63847529eac5bcfa7dcd1c79ed3d38c91bd0821e2390ee8eb90d7f569fff60fd811694d2dd19889ce5f2ef3bdebd160e5961b138ca65d2082395c9b58c84cc56df1c4eb828a990591ef38e4103018f891e7cef3dee0a18e45fa2494b2e29dfdf3cebec38a5bcf12217f87bd9eb8afb1c812507af7ab86b7cb01a8400f42585e2e29b20e4a7c0a43e343869e566fd919093b244555808a110bfe0346052b55c9625f83320d365fb13e2508e283f2a0dc4220d39008fe80b97c284e9c2b47ee2d91b736aff122d81bc40699dad720493d9c7b70d5aeb18c344ae4dad35353d9adc29873652027cf8175422c96835c2351044eb90a782529faf4ed667002b87d07cc027fe24d4bd4edfdd980733ecaed98e7ef839bb0870012df211f9c0150510ab074a92f29b08bba3ed722e158134ceed5a91ffa4f0736971ab520cf35b7e9cb15a7b507a5d0c62cec9442ecc9004f8c1f33deb6a2b9d038b416f9d8f0af38800502cbe75a848da0b12e2ecf95133f22e3f24586bcd4ae8f6d6669bbdedcd1946bcdda9859339575228d35cb93501b59643e6134b259a80ffb336265e68e198b2132fa44aeb2b2abb91a4a7fb5098670a81dd54a93600be081984ca0159aa2bd57f10da45fd25f5e2c85635100ba4daee28e1907a0f6be90f077e282764ea02f8c656f06c43bbc0866a3987b14e8b5fd4ded0b97b0dad08a7a80c4bd59c1fd8d51c91b898e2b22000bb0bf60f8003af0abfc0dc68f0d6ebc3ea5d572ce460baaf7da3451fae20f85264ee4afb8b8848e78712ea6b517d63421d294e95e3d41e96e6f11c1e4d7ba000d80f8a160ed411ef27fb1e4e69ecadc46b8d26d84374c2f4b43de9240032cbfcfdc7dc05b3d55c211e2fb9a1f1010ff3e5645a04ce99ff63cdd1d7b22a182812ee56aaf214e9b3b635a7ea31a84eaa1b4e2ffe6d2a2e70a6083b0be6537f3cc314e68172af443aa80171121f9e779dbee5c5e3b40213e2f343c048b8b901e94ecdca6cc604bc00ba78402a49622cb2c850d4c6e23f118911a84ca0581cbec9ae903d5aeacbb233d550d8247c22450ebf552e41f7094f7d92418e162616cbf3421325b4fb5edbee1009030fe3b360adfa007339fc4fc927783c116220050db5d30dc2b817d1089edff4baa434260ba42561adaa36bf952190bb56ac6f6ea48d960a59e3045458c58c0aeaa64e03450f12ab2a3d4a776d70df91d475549353025844579e71da32eb6009c52d501b7373acb53c8f9917702914b5a9616ca0d75791f52c68e360feaf5f4a925a96552eaee6408cc572d953eebd538c446bf0e6840086dd509a25e9f6ea0c443d18aba2500c1cd0a9592461f855534c39190029a1a2a0db2b2cdb897fd25b1b13dbd3ed74314afe52aa96c70f3b9fa2de2f556a968b66ca2083788c1ca4c1e81412ac4b99dcd313f11f1a11ac969147313227013bd62ef620873b7114bb7ba83830d863fae24b7db53433edbeb40dc6af3eb31e9f166b7d8a5773142ca0194780beede42f71d143d3805ab8eaf45df817e85234cdd151b666aab48d9f38151dc54e710224eed8af881b257187e2d2e1d708202d0eb3dd2c15b5505ab637debd53dbedea8b0afa29fff40495bfb3481a92132f68ab302b7d3b50152b1405dcd03d0e4bebebe1bb173e33e6fa804fc8f305dbc81f47537ec4e3a0eac526494423f6b92bd970279645c2236b8c5c586275773c15dd0cb5df9be8a5db7595d08f583e326c7b0971cea9fb3d143023d7f53f92ed87ecbc849e463c4431a2caba147ddb32323a94e5bcabb86b4cc7522c303658fbd1ab75a09f2362a422a052fda77afa6144ef01d94649d910f291afd736c46ef01265afafcf58cf1d8a52346d16971ca00b3abe9197d550ba3e715ad4872251c36a0a6651a7468be136d5f11f6a143f401794d2ed1ace939a389b650d1b7e78f0e325763608465834dde89acf1e9fa96eb813a17dec868f43b13c0245bb0379b715b78e3532a3183bd14af1bdb973da110734d4073efe61cf62ddd22e32dea94c1058221229070a2b2c61046f321e580597b3c49ea99e8e87b201731884efb6125584bc8e4ebb4901de73eb830abbac381d38693baf45d73059ca4493664912249d3bda7af88cd10a7d595e122817b8442225249f4d026953a0c791d16a9833fc8cec115044847b7be3b26514d0f1d02e051ff9734d9f0a297da1dd54f9f871c9bb66c0c3c1788aca6c278f95cb218ad37d21eb962215a6d4a1f7665e64931bddbc4dccc6e76dcd7b72fc846740fd070161b764bfaee3a0c5930d8294182438c9f389038093bd3d39aead8de88436beec98e4718198675132a6594c2228602a66bbc55640d77fa819def0bdbb56755584ddb7614f81d26f4325cc47d9883eff9bd8586d20375fde607f7daa1fb256f4f1e2a36b49b659912068aad002a49785a3a0eae19f5e7440bbe3ba73d1fc5e52704551a1e0add0fa9031905a6924f34adf4ab42bae1c8539c0d06767a16d6410d1c8e2ac9b23781082b8eb53f6eeb130ecc454cd65e1ab36b8f67a6fce2b8ba09d824ad4f2a43bf01a71ba81e9806035e2dfe9eb14ba5572b8eca391abe36bcd27c4a174d727b8cd60170f9fd072bb54ee4314e5e9987f79b335a8596784d6091e89d31c18abb0bc67bf3a9ea95114f361f897a347cf03050a8de80eff83bf7e5a00e7ce1da0f1db817cd2e46ad7d5bead88cde609a6137489a92ad093a5fe0fca05ff13d680d9f3c6954ed2f9ce63f292009becff789cd31eba5d5012cdb179753ba48b30648afba30f9ad40ff56e975fe983aa96a4ce1ee7fd5c7acbc8fdd426047a5acbba856740b19ae36ac4fce4da52e5a11dc5edfba54491c8095d3333611417f4b18f9aadb3a4f55100603bc35e2b011f4fdb95cc894036e09def44d1f05ff0632e0177424e1b5c6a18024673086dfb37fb81b388ef0c5068cdb3e089c48ccbfb6d46ba6db948fb50f94b819d1fccb165ad16cd2b103749e6c6c789408a3f7a5823798c222d658087cfcc69fce6bdcda53cd09ea4d0ce96e7157473e2697c068be64debe1063331025da78e7a86e3ed4b112a4d8c7d9d0aa2c8037d46353e4731cce6118395b67f2e39c8f4bb5329226db252bf136e1d89b2a44d391f5c749e8dd2515e12a7a7e3489c2ed4a1a7eccb0752105b93fe405d274e389c8f6150174cb5580f58a4266a49932160d153d41642fa3cadb76f6a7568d375ad952e0e15aab5bd62605c2769bc1151752466d9b8ecccf5f3659e6bcf051283a06e2cfefdb3d2517622edf6545ea8a652b8f3227dc507f051fe9e3a5a4e2ba6b5a2218c5c27400e4006f413ee79ca73fafda8516b9e5fd8bad52809b01a71cb71ee315fa9b7f13e924611ce1905ba7561e775539b0bed146cab73402ae3dd7fec526f73c0ba3cc1ac9ca31a2dc303a5b98728836fd7c2909e09aca0b1180c924d43087c59c867eca6f91887d24c454feb40095c4ef7fac369b35f7237bb8e000cf174bdacea759e73e915c2ad36e30f5a4b1746f98ee44ccd6db4be1e490b5d86104211e71d6a0e9ddf0068683dffc446d82ec0668fe59a7ae726d76e974501f576bcae950c6f64f0a4caab98ad9caed0de4d18b302f9630daa4759e2a973fb42796fa358191671f37b8a9b20b84c9c30fa7097f8c18af89ac631e3f0e5ac838ec6908b4300b7eaad90dabce2c8c8426d4d604bf0ec0d7a2c65f7362b144d92613d225a58e2db87d4f15d0d6b421779622a7220da0a0fa3c381fe3f7e5c6f562b86b4d9f3d2f6045ba5f204d83d93f02b62cf7783b443270e212655b57d6bd30cfb81e5122dc360a1975714f2e01a917ca9dcc6c7a0e743efc8676dc80550af76c0c1a11ffba4454c0e9100a5ad075824face437df5e813dae1e9883dee79ac1b3777532d7f57811cf6a1be3d0478318fa865d15677b4e5c9728c4ea0309f0ed1a5edaf961b03fe063a69bbcb1261931a2efc40c85432d17dc22ccb4da7bdcaaf5049d488416818c414f8a52f19890944da7dc8a8420a0ed03aea9670ce4b4d50ec27a781dff2a126e7f7f3c15be33d9e7a989d3166e2d26141f66bc86cb2e6dc625e3f9707b50075f7285da7ac06600fce7f15bb3d3ea6e4d1565be3a19dffce8a952331f885c0505ed07979d299478cb430868351bc4fcac0ebeed004391d0d07554b55f34b25bbe9a6bcb993533f1202900d78bc481a42c66ffbe1f50ba03264173fe0754724584f0cad6b2ab968f9c0dda10c06e81be2de35bd44cbabe28b235e29ac1b572ccaf190c8e88feb323aa0ed121f15fc2b3192322cb1ce25ae9df030ca9802a54c692f8a61cdb9693383c98b1a7aeb0c205b3c5a20e967123d38820fb19e14a0939a1b1c20605c85f2d3545ae8b4925874a95838e960118250f99cd0875f3c81d9725b7eaca37135d233fd51c17c2f3bf2a1add45610f3777fb15f491d84fdc5b2f88c9fc4ead6df6da09a5c956496e138afcefdaf5b675f0b93acd23093d364c5608092b71c8fc4af5f69f50fb9bf215242949ecf28430c43e41d750614d9a2e7dac7813a829d663b771185fded3b35e0867d62f81bec7a953fec41dbbb5399d9f4387330a341121077dc162105deacb871c349e0d6ec62f6c3078cd0e84119b5a61817faa2fdf6df5d3f633f97815a14bafc84f9c541572acbb0b6835a03ed18e7c65ef2a0ed0ac4f1d08c51310e058cfc614e91f1b020d605489a882e44f6bab2dfba9b53b1699a9205bc9f0e0a032f30797628352d962922e8277b88a10bc08d4d1fbb7c97dea24e4d8b0e3a3de25ac52c2853a4b47ed425cf40c74fa241229c66222e9dbdd629e114b656dd2fa0f60a1235348eb1b1dee74da3dcb9d5b6ffd1bebc54a997f7b3bb32ed1a60583dc1d77c95965eacde6dc91cd595d34d1f529a9989953b316fd464179afa0e5543ea229427bd079f320e1175f8480f260828ce648db5ac7d03cb2fbbd78c105b6038177d817e075425226af6a69d079d6964e432be5928c83dc0005ca6c0567f8b4551f2b1f3b7c91f3d72c9df7f0202beaae45ddb5cc39c2213c744d4f6e8a65680827b2f47efbe05d0780ad92b1fde4a2391cc47a49dd7b31071490fd65d76583d83e3fb4b694984b469b01d9be163cb82a2b95aada5c2124bb31e840b770c8c45f0a89663bb85c01ee3193cfbeb3b3cdf6cd8f3eb7cf9a7e30ebb3bbe598be148fa0a7cc2218e88e7d963af745965982c673a95c453d7e3b233c370c87354bebf393dfd637250aa660d15ee7db4857a72d6d381f361a9707bd8722b9d3733ad2f63ac967e44488cd83d9d9ecc2e5a76aa0483340aeb08afc4dfc3befb9682ae76a21c9e780521976dd1da9bb131228c9a5db831e8d60078dba46acb316f73dda551eac2c622ee9081cedd239917b93104758799d33f3ec8a436a45d2a01de2782fa8776f74260876d3976d3e980e5d29661c9d6fe914f972cc89fbab40d4dcb6c2067c0031235e74ca99ff8ac83add2f1172e42213543a0c8e414973665f503e1bb3c41e97e8350845697345896e7312ea3438dcec49b25ab116708ca7a73f3695b516f93dd3e5921d0a96f643c3321b4f471a70d93cc3637ce732a24a79f206d76348160f93ad9b80ad6421443defd2489d4be5ed64510e633057306fc75933e9550cbe719f166b153daca4c93c6bdc9d191742c8893959534c5389cf7dc16fd53cecdf950e0cfe1646214f06f16a5709458203af9fb37a9a0268afb59b33ac6e07800cafa7b6a93fd5086a01542e223ddd01b06acdc141fdf314cc97f6cbc700ef073c85e7e32c59932ae802c933545b102a19398697ed78f33231d1b4f6c9a71a418cec81c252c2e9151297e307517aa9ed1401459b2ecead8aace5b18bab7d26636056f459e6e5155357b54a5239ea662d0fa124291a9f3bbcedaf60dcf2b6fe698c9b6612c42515864ded3ca6fc6cba06dd752b8731205f124f03586e08f3452f8d36f1c9066fb5bc4877423eecbe91a09565f1389172943f5256e13a90f21e842d4fd152875b543bab9cd2c79dbe9d7aefeab768c3cb91584fd3628daae3bba81e908f358717c9f6e8872a8a9c41f4f2687eaf185a847258ee9b34bcc8afc24dd66ec682183b84fc99a502b2e56b0653918e3c4d78757a220689de49a47774bca0fddea74bba209580274b978d5f621fd3cfda8c800cecf637425632f0aba119cd195033f41450166ba50b98095fa59ff644c9e4dca6cf79ed88aa0da574910b8440f3eebabc7e41f811f4e3349c30037afe6fcf71989170e040774442ddbcec2858e11564721f99910d9d3be5c22362ad4db6dd6d2ad4c6146a3a94c1680a511b4c8452b06274da5d35aa0453ebd9f3d1f4c0ab75234282dff60c87ead6dbd67562d204b6bf8e70d430c2607bc354043b16a7867569b839ee61e39086f2d48fb68606705fd062d9f52504cab459dc7a40b0fa175d27c686badd0a4c4f00e5522eb7229f1183ae2a31714faba84892315e229ddd30a2fb642117321686e6eca5642599416e76cab4bce737176a115be34e644c09ec3ccc903284886512b70665fd89fc86ff6fb220566a0d91898a492679145fc048298fa760d0205209882229e63fcd983c68d3801329548f02e6e39cb20622d782b3d076275cf165f360db689602b3fbee33c5732806cf1a89bbfefb068d5a001a2bfb8a31fc5d1bf446edad72258d570f7d1c7a18f4bf129f4205fc434002fcc7f97b3aa2f6c5dd0a7e053d13c9431e07504f7932cf63b55fa539893a08468cb1c4f6e565eae5e6c78ffb9e7280da80fee59652f8e8d9debd9e9ef0746955d27391ba396158c53edf9606e7a51249bbc7c587960831600e4eb99604b7725e9bb593ac8828c745dea0c6450cfb76c1382b07fec110dd754e32805815923f803f7d9bcd10a0ed154eb029822e49f8ffc4b5d5bf3a52931bc307850523a7f96026a2734ffb71cdc1a8433067c2802187bc2ed56715996d40b44843467ceb24cba994afbf36914577eb2ce69b4e62434c12e3d81c3512cd8fc8ff0c20affd88427cda0a7064b7057304fce5243b252931b522f968e07693bf78d50a5134e40ffad97583a5aadf469b96feace7e508225baab7b884e5488c798fb2de458e2dcc4d7fb7a7fd957d24164edc9752ded8a9edf1628bb3758a202ed0816cca783e554c964da789b44eff3da5412d763a03cbbfa3796f3b8732666d23a7b80a97b3dec2319e6ff4d9a0ff914a44622eaa783f4138501641322db65e32ee351a60d3d6a56a350e50e9f2ab833b06f46fd65b60450afb2ad44a4d00886d05557de0290bb2117987338284c1549a8ecbcb0aa6f20dd977889cf1ea3e1e00a506b5a83b245a12bad8e0d2060beec90984754f642d5268d2c91f4d1ec60b73af661a0c8bd3c7a5f5fb8c6e85d5698a725422b262c7918d366ab235e35428f1acbeb9490d849b649f332c1df56678c64c8fc9c1c2927701ee65988cc710f86bdea4deffa37fa41d870dc06b777eceaffced4aea8c0513f30e0915e6bd7c8f8930294f74b81034b80fbaf3a6abdc4dd6db943dda6f172a7fa062395f4ca1290d3c11980e0cc901d58e3503a07cc8caeb291463dd837e373a62af2019640e2b0d88b78b1168c75c318e56c8f972daa3aecfbae02b4e1570d0cf36bbabb700066f545e3b205f7801695c8b8d84eac3d7c27ef613a01b96bd288a971acf492de9291e9e642b74b1a98372c41afb1f543c191d27b4e3f9052e4199f76967e620af5c4d8a8a3709e8285c37c09c14edb0ce39553fc1e8cc1e8090cb2da74e3d19c759c21f35b7ba06d32c5c97213dce22674306e6933d82cc55969196306059ee32e37b54918af8b851f22c10194c75127d9250aa2c696caf515d4912fe6ce792b7707754684f071614618d871ada5060f66ad75dea5ffdd574466f59fed8c39151919ce252e8e3a42cb15133801019b1e3314baf4ee2a71e8d74a92229c608b183d94d2aa2420a41453ae70c4efc84f2b2a9ea0ad692f047e1b25274e1aa5ec6279884a2246646817105b16b75926e1f0577cc66bd1f77bf61285acc5784783d9945535adba7941cfc1ed4e9616cd8ce90fc680bec9b14a4eb3fdf07bd73a960282a8bceeb18efa79e543a231ee578080342e0c8fe5a2c05002ac5c1d73a8b2dd042cb5ff17c407a0c6d3395618b2907073d6f8e3f36a8b1a25ad32e1645bd657d44c3416a6ce2d695102ac225b165359dfd805ff3d79c7edeb13bc6de021c076b476b84256fc8dac5a7eb6a7e2a5ad5187b781bdd4f18dbbaedfbaabeecac36b4b32c96f1410bee26f46435f069a856ce76726dafb63cc067ff5cfc095cb036ccb70c46633bf8c5d0be8ca4e6613c8e252d0c4215222c3d4161c542028b5048f0485dab8ba0a2abbbf3474af76ded67f51fad6ab29e958fc4677e5a1567809736a0aad32fec1f7acb8c57b07fef565eb6c40c41faf7e139755031c463e88e49667dcacc6273978568d3176ad1dd3397cbad426bc5f989e2ae10bda67b8aa6b40c5ee4a1f85fc88aff3527c305904c6dce20891595e476c9d45746345280a906413cb856d10d73a069eaa7db560ecd1149381c37854ca8f79203e50b35522847e8f0869fa9031d058cc88425f470b0bc501b840cc971c5770837c5fd41cf6dc2e1a012257d11055359b7105a84d710b803367385ecf177dc5c9e947adebed6e532082e26a977c1e9d0123746d43768e35183e80c0e156af6e9a092dce1dc0ae39c9c05205a32f49e237070df30a9cb13fd0ad0e13913744aa81f648543bc67d3cc8135914004d9c21c433c1223776510462ee5a52b11da163344891964b3efca57c289e9890fd419ba08504b03b4a6f242ee3d76f35d723e911370387d0bd733afd2a2662de764fbbc7a9ea5fe01ae111e82f2252b1d2766393260faf2df22aace5517fb6e027ac9e4b1d5d662428c51e5ae5909cf8c289ee0bdd8ca961a3e14a8265ceb5b9eeb78cd899bfbb42ad3b663063302a008d22ebe6e7cd907860d897c6aa97b0140a1ceb6721d826ccb08c5a28fa67f8be54b22a48055f7663a92caddb60aaf30f6720b173044a81642ac23fa247c628f220c5c41fc816707a7df45c71ed6ad69c1e73c754d6f890e6426cc68bf165452ef5d465ba6cbf7c967e40b21c30274687ca23958dc04fa7dde7eabf3dd69c0dd0b0e719cd0f3220d384208dd871644f1ed31c79e610fadd59b73e86db25b0117a562eac84e46c5a71912f2b8192ed2081f876e4e9bb8830ed8945b47aa39152c017242db6b47fe4dfaa5d951616df04d9f10d4e26febc3334af3b167994986485f6e59afe5a4d66409a9cffdef8ca5a023f294dc0502d3bc8b94106ada777167338590804469e77da707f663860244759ddc77260b0dee39ebadfacea89de8dc01a85273b3339cc3cb87dd7a66054b821fd51b0addca1751e34504220ba4dcee498769fdc31a762f77bdfee32044e3971fad115463ae3c42994aae044a2b957bcec24cc2eb71a9829ddcd73473da9ddc6421f501dbc432a9465169e650196c9a42892700d68d10cb38fa8ea089d24bd0e57c49b7c40aaf49d97cefc643a141410bc7f639b9f312c7f49255333b933d13f33a33b500dce2f3c8b2babddf6770a6c11808079d6d026a8b36203b9d35122bdda847f2d0bb207188e1ab35971f776b39b9fb52f6d17894bb7169fd434189e1a85808fbca81de4f9d9c9c3a9ca187325792499c4ebb4c72fcb3e2a3f72b2225b125af5363da35765d47886fd7fd7a08f8cdaac2f4fc06e4bdde12a1a20c6eab8159472a103df9cf73dd1fa69f17c62c9bc842e6654d472e76973fb58b68e3e509bb7b9a1ffeafd688d6bd4e1d0f5bb6d1ded480b164c22b437efa8622c7783caef683a5107a45c20bd5dd60ca9bb796b248f3d9e1a543014a41f7d42ce4b853b8071b87bb7b975be505cb7eafbfacf90b48f790c9898f95f984c4e31b2b32187c3a279eeb1885c74e7ea5330a0b539bf13b946df02a612f69c59a25717b017eace1c324d70adde6dbbbec157b62bd4fb8c19babfdad5246d53e7c5cf8b825f7bf9414680f43eec73f0b04584dafd5378493d173c5d93868721b27ef65ab20923a63ff50397a133fa9e9e2f71a1fcf448d7250a72d05c9d95a3ce2e6cd2c8cd90d5e6fd14af44ac9957bb55d50ff9edf986c639f51df01db32530ec8e3ac4b73eb1a7de8e31337752dca31e550eb4dfa015917add5ebfd785f58fbe79926689e43ef3a95ea5234be4e30687e06d23b8cf475cc91c0c0bd47557eb19d13b5d2896ca6bf26f6d3109d2f037bfcecd25652c9c035452254b022680e30e7bab2a8bda6b25d0cb119f88b6a312a74b254ed79cdb42119e4a025faf1fa9cf62ac2636e10d14938f47f6bb338ad163b93d5e6fb5cdffc11397e50b616fe6802c1b47ed2f9fa47c9c761ae3d85dd6ed039d73e4748104e60d397f3790d9dada52f60282dec3a9230218ba0fb9394de68aa9659f770ca50037fe923b86c7d410cc31bc6f6f233412ea93c85fddaa24e9f422abdf5ca199c0285259d1f5a94dba8e9b5112d85c994a8417fca2d76ab5fd092f0183d503766b19ce311cf94e1be9ffd4ad61966181b3fb02e97a0dc8d443f5dd43a24020c038a8e434174e2116e0b45512a9ae4a384978322be7a3fc646ac86fe4d7623f785924cc17ee3075ba96f0a4e079f45b74e2941a1b57babf4bdc4a7b168c8c7bff503e04b5ba6acbff0e965e306f7c20b8023fcd400f7dd5800dcc44056b2fb62a8a7a732a229a59d57e7111492e384f6e34d2a4a37dcf4baff9db3c271ef58b369c85f10dafc61911cbeb1b5680beb6aa784bd59f453bfb3624ae76c1d59b4623bcad3847634994b4f609504adba68be9bbf21be961127a8304e8f84394f066b725f464bc5e64f8a37a5f2b92cb10a2c072dc66a71af5f88f5ee2d59d14eb390e893050a04b5a5fdd7e2a8cbf889a9074ccbeec2de4505eca88d96736349bccdca373d0be9963ee598d516206dd43f2e9d3bc67583b774c7e063c0c599822277e542cb24604b1aded44e4d32c40764e2ab1f2751c431d720b04a5319ab5951e0abc9576655ed47d43c67b33fbf4fa1db9d9f28605e9624c230293e1607475cade234a9e3f6bbb9c7a72ae217857500c8d12e9203e9e64d58a5f5d68f926d7832d77ae14819db9bc8baf39818e8db82f623b908c751e7b528a35ea03dcdc7fedaa0864c4af93d9c8f1541c7e7a94aa729213c8e2c1b60cfc2a6e101f3e715b97c755304440da0816a39d05b9b8cbecbc403d95f65dd6f324ad162e1d09678944066a2974bc14296c633df4885524c4fef3cca8391354462d10c9b259270c27b977c7a874872872ba3723b8a0fabff4e48c0a8f4c6ddf1d124c3ab95a1614f93ca1a548e2630a914bee9e7d3105541afaa9218bd2181d6083c5c02eb645f5c72bd3ecabae51161d8d0f94f569ae0a6bd33b40c057657898d606a940c40698e70baebf37da6e8dfbcf4a260d65173200de50f35d8362b3c2f175d5950afcc3fe4a7ac0dbec6167e0387bbc751d1648f207c80979504d20106fef3e1e3f8a1e91628b962b5862b009ce10b4723ad7a40af3902ce7d8c4185187890c0913bb90cb3c4addde6cde547050d798428e0672fdf08c04a9ad2f7f956da5fd21016bb5588ec08c5bce500990a7f10c2b256a3d8c2727decf581cae7c1295979b1a21e1d5f611306c13adc0648b3c77b2acb40680844ab18742fd2dccccaea4691d5e0590cda32060c846fb44fb823922eb1d484e2c417fcbe327517ac2dcf9cdc8ff8911fc59253de5fb4f9e4a330d71447e108d5b94d5527567dbb581130e0a4adbfea71373bc2b01b40f4e159b7ca84a1e22bb3d10a2feb0ee30a605c8ac8eabcaf76c123ac212d19519161d297342e85d6fd3c1448f1d0d8e79decd16f59184cdc1b545d29ef67b2ea4feaf6953b1ec2410457faf9c25c7e1b1a37d274a0e3eafcbb79f090f8bee72c5a4462dd8b2f32e8ab88b152e650d30e9d64b49bee227a0a97834eb1f4b912b5ed12a6514978ab3e77b75465602910e57623d2e2cd9ee58dde41edab0e3cd51f6d7b4f05179102a7c9d3f8557bc2f7450ec9289c29d6055306d3297a48172b9e3aeb46a0813ba636115e18ef7c601373e51218fdb068d7548599855aa1922a5b58f651d75408ff86e1ecbb3ebe62510d761514616170be1b3cbfaa4f64201caea206a889f7e225cdc1ea3341ad9768bd709ceaef99627963cf9c549819d7412e98c98d8322fd1ebc152c1fc88b207da6ace3320fc7231ed2b50a2d4554fac84a8355b1756657345574db5c5d85d5196e7e3d9514a875db2f2a14b598c0e3c250b9e3090db991405796c5d7040215abc31d70d40553906b46b28f016cdac51f3d21fce2c54bc95194b883506066d9c0ac4eee8855a0d87d0cf517f7a586dbec7cf6296783e17f79b32e3e2294374c86cf63a58e591b76923fbe64f5ecf68ed00daacfd0cb79e6d2e9dfa982","isRememberEnabled":true,"rememberDurationInDays":0,"staticryptSaltUniqueVariableName":"e58622878c5b4107a5c053c29b821537"};
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
