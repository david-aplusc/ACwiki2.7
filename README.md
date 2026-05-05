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

        
        const staticryptConfig = {"staticryptEncryptedMsgUniqueVariableName":"3e851d69107c0329cefa6f927aaf47f0693b8a70e247263daf9ece2b9fb859552c8aeb1305889c5ec1ce6db4cb2d767eb0b00ebef6ac50d93a17b1c68cd3eb8fb75555ae781d87236de0ba2bcc2b5212d7a3db6f9077e4c65c9d79d938bd25d44f81bebb446169b5a1e1be2e133b937428174b6f8b8b36c67abf9c948796b2c91b338ffa9991cf86be33fc99db500ff46193180d8ed18197c63537dbacd761e42f9d6f50690d967b654d9e36d05750218b99311b85b4f913cdea11b4466c9bd7fadf7b82369d4ccc7fb879954705fb134a658bce0f817ab93831ee82639ea7f786a0f3a6cae59159ca9504e4f70790313d31b753a27323b68e6696265bf19b88d3ecb83fe31369cfe8b580152b7062dc8dd4047ec3b9ecf91bb538cbc7dcffa72893fcb03cb7fcafe4a9247e332108f4ca890c966210b3977094e017a87ceb7c57028caa189ab168fb9731cde4f0ac8d3c78c1ec65d314af3fadf31e086f7e973efc8f2717767a5ec0d854a9ae7ebcb99dfdf70839f26314ee00a5a6842a0b57ca808341b6a2b71322a88bcf3b3646a310ff54c0d4969caca94141b555f8fde9797ba905004b3ab52446d41329a4ed07efebd4b3548108a845048f4fc5e969131f862bc7b23c3689d4f39d38f63bf70237f8c56a674bde27c71a993491feee728b1d5169de49c8f5e24bd8e45848cdf6d18acc9e73ec57525e70ed059323e6b146518193ed599f829bac58f2ec2898b2e6156229d8815eaf6a7c400a9a43b8ac0eb00695cc7972a29b0a5a5e414399b6398e5fe96e24265b2da250e586d74ce97e0ec48ed70dd995bb550f179ff1c9b3bb8f4e95d35c63773440bde9f3cde9b16309791fc967c18267d3ee9817a1de0798dac31af16787824716856948bdcb4814b4cb55928ade89fd687e7931a3203d9707fa54e562a946327e1b2cbc9e0848f12756c930a8a36037afac90dd3c1cc56082489951d7766983cd171d69da91eabd57f5b5a69b396db7fc1be7f28918714176a6f716c40ef29a4d68e01a61a35b70b1c8d4f1f01bb0906a570c3b87befb3af9e249f18392effe17a81dba0c7172198cd82107fd9d633d62e2e8ad9800c637d3e10fad6ecaf17346b6b1256282211db558046b68a7b514d2b4b4c6558b9063ace5fc0f05e0a7389150e6f249f30062bd5c26fc1065e19a29d276cde117fd2234187ff112482aee4be2e96111b7530fc12d4f085b422c591cf772ad48f284b099c6970ecdeb832c4d74bd56be04c952aaa2561a9ec8e0f9621dd74255a3dd1cc7e4426e89704610b94d7540d15e40d8b51bfa7585f19f37001cdcc033cab9d7811fc4a35ce37c866516f404e88fdee657525104a52badcee858308950e791cb5e9f1c5269e99b9239909f6a15c148f2a6b3bcb38c6dedac0a85add385d8eefd4dc4f3a0417ae6af1d3a95851131e382d6d8c7dae0ed2b2f31ab75ecc45af24dbfa8ef4ed09d35ed6309289edbe9ac68ee50b554ce588ec4d1dd6adc0df73f27369c2f9939deebb0b8be885f89f6f371861f3d6be81aab26dce2ee27476cb398ce68a750b24c4bc77554d23b3c6bd865f77c4c806050a490e181892415fc29669015d7fea8688cce5e8709f82afee6449f5414234a88b34c9dea05b8c97a90cef5203655d8b6ba8db311f055b49fe56fda81de3d08be460ae8a2ff0f4648667f39bcd37a5ed068f6dbaa9747bbd47168ce307008ad5c95260b76e2c2dfe397fbd25f6f43552940c629d6f0fdf8499c00405694742236786a96af20bd30a56398ff11ad6a430c2a460bf686202e8d5a61b7e5a0037aa2b5b38b97eef0021c3058181edbb7aba8dc07983539fcbfe35f5eaf6f69aa18be47cd17980e07b409b6e2329791496c26091c8a049f13748c6df1d58d378625d16e95a0c6e94d1b75da9eb8109a668a289a0cf015dc188c61eab4884e58f1e0d3733f33cf72f7b7189a454053179609d45b5034e34ef01684253e87ccb3e45458431765e4cbf54f925826f029ad05cb3d8cff50418cb672846ca4a790eb03dce5bc34616c3843bc6d922a7e6f2818a72e8d36fe88ab01eb9d3abb107e7f0be19bc8222b19e2709cfd55808c5c1b5d1644b3afd3b33a9a5102df5a330f6b55745f332b151e58808fe25c4e1b92dbef15d4091c59e5539c3260a10e4f0b83ea2997c20a948badc005556507488602a2f6fe54ebd50451e2fb83fb1a675cde7a493e76adb68a5c48d7b4ac34cc4cdd37c918b222c78c5c069cc592024b5af236ba0f2f562e2e7d960a8bb049692414a2eb8e480165dc20f0e1a14062cfff084cb12741e2346fce2c3ecf612b6a3b92955e178bd2180bd23fff79f3a8241ca2235573a1f4b485e3bed386f46455e43763294f77b83b8de8af57c9aba0306aa1a4d194f535c9c2f4b0d544ada6d693553a9c999804fe13c3bc3cf478e6a9aa32a405084b1a1c71b752ddf761341e595558e0b2a28336cf30674e866270d9ae121f1e24d6230735b57a7ee68b45e4020719a64f245512b7471d7b94a0305305a8661465d879aa99f573b4efeb1769ec9c404f5ba20a46575230b934543540b472cb3ac25beec460905a8b90db7ebfde95f21bcedac274e4a4f26fa4abc2488e2af02d2e412ef467c005592e9f36868919c4c6c567c449f75509c707131ff0578c2a33c3a1db80331050c4ec06559ca96d0ee0b5f3016d462d510222985593b9903c32466af3a7d3a32a7d4ad235e4a3f9fff03e2d5e4108944c7c071a1fda0aaed1dbf1e4e1859549eb8b886c6a233b570298b3584fdfa83be1be855f07ae683035cb74f5b8cf1c1ecfbe3bb2016c88938832b4d63fa78f881f904579d8b465ffa8bee15a4efaf2f09fcc352bbe8a345455c5ca013256ba626f6e10976e1791ed5132d1ec906692e4e02add973c1e3cc5a84374be64bed623043c8b1a02b60004bda3fbc75a09fe14b25510b534b7f67e64af7303389cf39109cd82088c0160229d75611dcc716186808230eeb8ca91979e19958b5afc7da7a5af6bc68f4868a4782edb6ef4e95eafb4d0b4b01fd4f39d168932a7eed3cc1db56271b9d70c6c2ff1a53200c7d2daf890dd866b0f513ee3b1d9c94f1b688764d2e2534c80c1596da9a217773b9c6824281cd6202388795b18c9de761a1ac30a5ff6307bf398a253cb1ba459c349253240e874ffc25baedb70adae059ca9eaf604948747166602b14eb20f323178c23a326356a814c23ac754dddd7cd299f309267faee28f7f16cf17f783fc4fb8937088e0613804f71fc077500a749ac432cef26e1c83cdffa6a3cd5c151accf6ba1201e4d62514ebce4816beb12032578704350367de7f1a0448af4c43c2eacae0710a2f60bf2d56e6b09e0dfdf42507a6165fb2ff07a6ce9922c4ddae4bfd665da01ddfdaac0c3e9ccd7f793f0f0e7beac68b79054867440c6b38ea7b837e3b92204d8b1d93c4b3e2814258e327668517d588809e45da0b3913571d3400dd9e8c7ac87e379d6760a30613483e658169da1e884c00a3db6dbffdaf5ca94c73a708133bb278f923bca40d1026a399ec89e66b9c0486de9ff319adf464cf72fb3110ffd1941e6be0ff70ebc0e00f7f5d91ea8829a8695befdc978453433533926d6e81e59f57a1bfe9712dc8dc8b5de81b4f51a07471283eebafa8f2bbc890f51067af57a9f6424dac1021ff47a2dd571eb4d033494986e420a62523fe13d12dadd25e81bbc495944249179dd806c86ed658a690ec97a0eeafd31ea1f98fd139713be6d3fa630d4a17bdc162f9240f739ea2e7e1aa25a132c8df2f1f69eb3eb64639166375628ea3ec189036bd4464371afc01cccf2fcc977321d2e6dbc06e24348a9425688b916d889c5108dd3db94575b1ec69c4fedf6a6c683ed242a2bd3173db7c1acb04a11c5fe75bcc638c9a65b45c7edf7721b0ffe89e7fec70899ae72c3dbc8dff4e37c89687d291a39155070ae3ef98104bf74e77cfc12d7ed061ecbd0e2c4b1edb5a9aa6508a37147bbe11f038b15f2b0f9963b5d6529bd4cc1f93c5de4f62782e89b81e00489b5224b7049b5634a8fdb0be7e25baa5a51525c4c878add3050a22327d878977c75b971421c25a8b2e5c1d1e92bea9cf4250eedf2471ad3d0b569b770c7528a8afd2706b6bb27e4529ff017b1f7e88e5080349e72112e722f8a164abc68f4d67ec8196cc3de9a8aea901e7bf1e17c3a4cb9fd1e9ac2aac85543974b289849b41b05f7c77bdd857cffb58add5db0e471b0ca31e7146471e6657de3c7736e1fd782fb92f27c7dadc881a956a64a131bb1fdd9380bc1000d2a4666163140fb3a932a80c5b1956934ab4ca642be52eac0a362d23057e09b485b9ff912224aa0dacf5ddbea340afb8778942b96536454a906398aa61eb29ef9400478fd2660cc5581402894f6ab613e6ed937aeb1c3bce54120b1561869d75c7822fed862b7dc5cd447d630a974cc3d2dd3b5c262e6817e419f26157a3ede1c354fb942660b64c63660a9e3b5862690af66b5438afcf7a4aa1f53263a9950d7df6be7a209ea7dbb01ab2f5103df8eb4c651f8354f8ec2f697b65795d8cccf01d0747d0e9f4e371d882d42f4815185901cc888cab50fa7220f5f247bb645680bdb1620d16c987d3082fed80ac158cb6c3bebc8e02680a4c0407c7702abc2c2ba6ac06cda780660f19dec09ae934c493d563db6a5ac985cadfbd29ea7c84df4ab4bf3e923bb5b16cee7c0b40d558234ac0ff292d96cf7638565d9a0b88a9a18960571d7f6e40bf610d98e20f2de858af9cd7a9b8e2a5b8bf6a5cd698d45040d032ad9fb7f1f19c7e4e5630ee663d879ecd64c97af1942b6f6e980682de8119360b79cc2f2c3c99895b203be5fc77f6f3184b4b0df79d796f077de106919ac0a6599f2bf670eadf2e23683f9ba78de1983a355cd619722a8161edd1d13bf3c88976f3c52ecaf5b219e50e07a10882583f9f5ac940ce9c10f2b69c85300ccd1632161e0f1c23c14dd732f447b23162b599da02f700014c41f610607fcf1362f456a9ca6b92890b190cad0c14e42fd7df07bf8fa1884023e787335a036f6dfa2253a089eee02ddab325b0b7e08b7eae1f9df8f15499516a02084eec45d12a9c0ae6935c18597eaeaeb5daf3d1bfc5b79b5dd214580ac1a052b3f5e020bb17102d0ef7c78ac330fdd6d0af8883591147e0f731dd668b93884aa808ffe5f066068a6f9238d5fb6f9c04649f68dea4515f52f5c9ff453a193d6e3653084ab80abbacc38d64b62447a35eb92f9a950e503be39e78a2936dc4b5d6cbd6505493b2887a94276e8ea3b7d97c9d8d09fa2fa34034765a784e2fdd2a58258e19135e4fcf606ed2bfa69cb1cf8e0e000d3b03e818972e020d30dbdfdfb511265d64a3bba3856fba41adfb02f0692c71ca6a64cfb56efe948f25f84f45049af256363c83f496fa95fc9c19b6c503500d9124821e535368985e9ad3ec584f3a5f46ac7988f2205e95d8f025bba85585816abab7e3b403142ad986eaf637078c19b6b3b5332a15f19e2ca4ab89425ecdc49351fd0f7baff84c3759b0becba64a3719712839c479dcec85bed5a6530667fa96d7c37621b3041a2e02b7bc20569757c5d686908217f34651a8261f33bf05975b6f3482b33cecb4fddc21061a1891890e5f5f0607494ed8f438fae961e42ae3c6b9bf10d7ba9b9e60a4d7d147e92aa49f3b4e31907aa3616e9a4a7ad0087bec7971c8b9bd8e0938e72b836cd04d4782a234f2d893509a4ba08d4e8b4a4b0b979ffc48634ba89b043baba2ce4442b832b3f4a77c41625645f448879a552113179e949691fe169d50df448871f05723d929d487681d51d69c6810693795c5325d67a9bf694d9098881783b83c1d458b441397637303dea7281e9684388934e84690dc6ff386b1ae9c8cfb90c3c44ffdade2a7679eda06997268568f51f384b05eaaa6725b41582ac53cb25b4dcfdba1b241500a2c9e0533917a58766419fa57343f175c9ae6995dbabd48f05648c5e66ea9189e5e299ef87c44a039aecc3abadb3114b0d446281313a0525e51f4b5d8e6f647a5570d1977276c3c503d5776b57a01f38acb4709dd78e7cf949bfca855d1a7ee2080748e6611915eddfe721398c8fa89517f675ae86aae97611b6c59cfe11db3937c95fb283d06e5aab2ad294b0bfcb439a455fa9fba3e0c51eaed9cb61c3c6375af0831444260af1005aeab60950c1a22f56545066cd0ff3612f2dc6bab4dc7df393c71940e12e906badcda2763e691e8a1d742f4707b702f3d18ef54417c6594c99d0d0c094691fe54235eb5dd5549b2c28ad3dc1a570b2135f49223962b24d880b7c3685b60e20d0985c553a66074e3500fac890b77fda782260473c52c916c494654950d9e5389e50790157608a9f7089ec4521607c5e6cbc32c139a55b1d2ed760cb9db1a4af2b7852c8b672fa3d33975ee4c28d388025a22806aae136f2958916205e4a38964b30087e30f7c11e55f02a18f98f8f93a5e42f1b55bbebe32fb1f8b9383df047af11663e2373d948fd593d27b06a7c4a2560188c014daf66afe043ead3336b0cd1a3b55575283b996e5d1e7c04ab6427aa06685dbd86c3ad4cd7664ce14bd59a3cadd83884202806b4a5e5afa008f13f3ffc290838297e6f1990657bf350d08d7b690408859b76880d288a48e0c9f4916d2ee025f60a83154ca5e0fb294e298c646e71383629772fe16bbf95842b597fca950343cc43d1ec45b7d7921832b2f61278f6ec75fd2e4091ce92148c6b4e9d2e4e07aad0642735e91df003bf32a53e7a6bbf648fffbc35c5c7945a208c6000eed5b807e61134bd82fe4a6f5b484fff3920f74129344cdbbb7cd30ea82c0367df1441257c89750354e713977ad0c5096a67e52a7879fcab5c08cdad3941f97598faa09995c28a62ab638ab5afd4fe5754968ec7560a58c18d374c0b82985edf156196e0135c874155a99eefb5883013a1d16ff8f75875f4dca6dad2ab79c2ec0412b926ce2f8f2eebdf59ffc5c25d89e98cd7452f3fe686ddcf32f3ed9b4331c853dccaac02f540d9fa2b52e223c3a1823ceae00eb3ec97b0eb18a0a749595775bd3728df682520b6a044bc8db9eee7c89c26f4dec615f5d721d9e88ef6df44d36619ccb85dd2eeaa5dd0a4ae68c3d15f302e2766ae8d18b1d4f698c7b3fafae0a2423f0926f8519468eb82d1bceec783971dc81419b3cbc0279c506e99e6f61bc229043fe8598a1bc2b896cb453a704b4ef1262c4ee94c16cfb53ce8425df65cfdbb40a4257c4231029f21e94daca4aaf95686aa354a48d8729cac927e9282d179c77377f7c8706441a4086687fc69a86d1567d1036e0edb0cef40ffab2b9e260645e1cfb83f5e754bdfe741f02b496541500070907098da5ee65a5662541efb99fea89b69d6e54c51f988818586dfd0f1721b482b4ab0ebf1aed36a328da7ca846f7a1e28c4d283905524b78258340ab2b4ede794c88beb72ac3c2dd463337f9bc9e98de5a81a594b2bec0e4a5a94f529a39be48d2bca5b7bdec251cad6efc714b8898574e156b8edb238e010a793758f2ece248b3306113244981bdb13a0bc7002eaf0c45f32ddccc1cd78129b6cd7e42ca158ca5e0863c2cb8d2745fc84d24f55252f4fa2fb04d4c4c1bf5db15c7770441823c94d21d82fa0636edee143b908e628cdba04847ca936d35a17668f8579da0acdb385775f41086973d4062a47158c1382ad74660fb14a4bcca9798392d5bc0c6d11cd6fb17623bea4f8c8c20f4b86f99137b637e4b7cffa35f5fc9184d7626522a632d878dd320473d206f31e1a84a2109a3410d0e5d0edbc940fb3ced3f0858121fa4ba8d6a39a73a6ca22891e71a7d85b93b46deb45913fc5164f16089e06d09702386aae2431db6203259d8a71ad78cf469dc630fe53596feece4a1e2d216b240f1468eb72549f942a2b4245669f500aa3418924c33b296e7d1f910ade7320c9e03e9c3965a478464488126eda69cd8c4ccdf1cbe0b17321ef4e3b51eba5eb958e0bf9560e164f62e834f26316584f95bf4ba3733f5cd66b747e6559347abfbb6224c614da1c2bdf9cf4b40d7c19786ded9b0b844be2a2966828280bcf5de13b92c62ac6ae0d56fb07088d6f1f986e697fa9f74d0cf466c4a94de424f2cfa019a5614c91d7abb0b7855bd752dc0c6a41cf4b34b0ddda6638eb5bb69f4a760632f296afbb39f6901c4132e11676b0604d152da6fd32851fe54c9734dd2f9772e4a5f42937169a5fa79f901742ea3ec755d392c399181576bbc187bb22517c7eaece4c3976e46ab73450129cf610a7e39db4e662093fe347bf3940a9b01acbb88be857eca6accd11242738ef67555ff8f0d8482b81b43a72975053f830c44dd0e331184427b4ca79cd432445d84570f4ec8ca39e8b3668e68deb93775f320eb1f7dde18e3818510fb05d54b05bedb23b02d69f0d4347ceb9e10146a39b4b00c291afa231fbcaa0ee8c999e086e28f5e9bffa8fcf579fdeb2cf6c4085c6bfe05b79e659190a763328e5c4fdf8c9e04e79f26381c8951ac758c672a7335e5745ccc9a739c379106aaa7c5fe95bd5efbfc22a53e1ab7aedee6b8d5b533b1e90c693b6dec2a8e13705b5784b1730c57073f52ba5e317098460bcdd52ae1c8d1d24bd1ba857dc747089b8bfa44763043bc9708da74049b2c6818db54df435aa768f9da4a1b4465292a4600232e23601e6833846202937efd34554d37cd0622f0f9279a7c1ec871b3b4e9b2555bae326f9c641024a38d687b6437075f6fa35f351050036cfd915e6862a0b70595f183ed494b14c1daba175a90661c98f7d20d4f21d454f3a1f71c659df51314608737f2d131735f06f814524af4b650935445cd833a824ddaf5e1b74c48cdefeed0d5554bc8939cf3a4c1067577872ddb8f306678a99bad855f8e777b64c392aebd0ae99e9dbd04b5b15e33c23be011246a6aac15a4c7d7440213a2b87e2b738c3053450795af059e55cfaae011408acbb7aa6773876dca303c9490b82b7a9d5d13a531b1163a79920d00a55293fd210236e153853be0a50359655a201509af1eb47abd499ec2e8b759effef88868fd665b8637782985f09fe708144505e7b567985522b23051da2740f3cc0380de87e6cb983e593c6318f7c5dfd886ee86004a52c4543d7b7bf88cf3f07ae8d4f61ee409c05886e80f602d31c830ed2cb30bdfae5f2a66fdd04b515f6778bcbd5923011309b282bd3a8dc800de3868e4d5d2d91f2ce26cdd1020f18eb2574e30eb123ae24b6fb53aa21e7aaf47ca966146562250192d609506c2bf929362c5ef12c0a175fc95ededec6b51476f5f8be5ddf60193be6bad915e4b25c13a82d3ea3fd9752ccc4665251e06142526b53e3c2d8b346ae6a0eaabf24859e81c130e5b901ecef3236d144045dc3098b2ac26ddf7aef34df11c623dbf46907d8c56589cbf2641952bdcf6d747ae0cf45297fc8f1f4b543ce683da57f5b4aca06f3a8cf10b98b8ae1d89f1aa336a02d2d4d73bf058daf7fdf147d5c2af847713977a453199c4ac825f125cafa816f1ea496f940a220eb01208a2fcc60c4ff46d4571871c559411b257016ecfb994d09383aa698f216192d5904db0c5e143126d27c0f82de40a8357aeb61fddd7f53cff769517afe1cf6c236ce65b57df36f108896d04ccc64b441af280d4500874e5d46eb838ada701cf3f2f1f0854419766871cea6934d3efb7975db05436fdad78cfd1c480d2a4b473821541830f97ce1d3905eb202d8517385e6d1562fb95b3dad9998399be4a4f24a546338a37e542502c12c0a19aa7afe7556e5cdbd2ee470244f3504964ad045a5b1647acfbc0983550bea0c931da60942c8f6edce348c8db69c3789f0568263be32514ec98de86c60d311ca64715d9b29e21c3f50dd98851733f74a59c29c2613dc3e7dee60694cfd65c96f064729faf3997ee746b69c0e6296935c532bd9b1662fa15bacd6b85a98a92ab49965587b2f3c884f1c390f87a5844e6692408a2c7d2e2c97bdf22929c6eb1e7caa2fbc8454bd635791e72dbac5923c7062ab80610a32d2ed1eba1ea25e36dd961f6b355a8698223b8bca82be73e6b7304b3d3ad3fe657f1dfb89bf6a87bd975a7d29a7a90697b8d1575c926e3fb82ef5ab2424b6c3757cc836b2471913b5cd02daa45b10bd6e73e8c802c4d63b90e61a0d764dd8cadb88e1fbae9f7aada695a271c1ad2e03e6d859ad05133d1846eb8a638d7f3aad16dee07dec350072443b6e420faaf2793b351c37ba7d5b92853312f3a834615b5f1e6852c8e2265a8a9d51de3ae9a17ae8bedd7c4f5d444e76748dc5f0f85154b47ded8d376ee25b31716545502c57beff1aee0a65e8b097f3ecd333deb084f0aa2aa017b9f3f5431e7efb57d71fdde5e21e4303fad4e01e99a32232f3646398002a480d14ab97bef536c2b505f49d4619ad9f7be627b8778df6cfcf2ed7c19852af33d50a3227b3293c6c90510ab5e096a2bab1261931d454006dbed93f4ad2dc113d4719192650dfc20b84ce0bfb678e716b603fd9046f7749ccf31146f6dccedd362e2bc9ebcfb322c56f8be03bd2bba556e39a1616c10b6bb80f803991e47d35dbfa91c9d51b8fd49683b314353f638d8d726ade1977002c1b2ff9a6308720e7057ecbb80aaf8e324705aad602f927f5c9e26e213faeb10964f11377c9861b3049cb99dfe3989957baf04c2cc6eebd156d01f5507f5ac2296d04602840688443eeed1dac30f394f53cabbf9eb2bd858ab9f043a1846f9fdc74768aee7860a2036366e357c2a69fac942cdb88d6b52a7788b8057724eea09031731bfebd158549bdf6a7aa521410ca7a4f2b3df90392744f09c313d100b8c0461423a64d0b7ddea840a795ee223bfc07c5de4a09d442166775e37b05cc0ce64ca92366245398d45886a66aa4b27c9dfb79e60eb2b060ff120534ccf0e5ac9f05882a35e8a03be3c2135caf4959305ba7d012d64210d2adbc5f22da1f0a1ec768b7398c8c365a9a4251311ccd945caaa4c8ed173820b38d95fe959cdd0fdcd4b27d3bf8e10bd20c2f3b40fa5691eec7274de43838b96956e130e26129afd55f71d39614a2a37631f910e88bb1b57d576be17f249f588eeed165f5b4511e521044c9f3356d61b35222437a8ba79a4461e9719c53badd89d837e8b3c03c9f6a3c2559254a45e4e34ae8407cfee3212a4e9227abfc68cbb8ce7086c05f68b7bf4d148e84ac5e86f4c60d1fd41ca4d88505914cddc25244ee2f6a55292ed532cc6a94ebd5566fbffa1d1e666e174f7fd4763a54e92a024ca72583e116a655d2b731af93f2c531369879e9a667154f551c154c13bdb9de165801a13acfb403aa0b12f7f2dc27a6bf536b7e5f0faf99f8a2412e5412e45cb08c1699abbff60a502f972985a76b531f058cad60d9b12e6fc0e2a493e15a77e514961abf84adbb88b078c689b818b0f7da5b96e54b8c2d2d4d503a9d297386d1e036e24ee43b68f83068adb4802052e164c2530fbaa38ed4f4fe856df676ac3b3aee3b52232d3cc288847255a7ff0ef5dff95b2eb6ba421ec07e1a1b2c0781097955625ed39079895da7a0e5274f27dc697345fe937f64a871fe18b7c9d1d858e9274322868f17b1a7521e384c841d2515fcd4f1eda1fcb7fdaf9c4198bbafb82815343aadacc38fe32110bd69bd07d5d739825b69adc9f473d2b2eb1559f0849bbcac33127576cdbb0a6c4cf642710c2bc68b3ad62a3ae04faa8a4993a7b5af6efd38a86ac9c1d334743b9e8a29e0c54137a86a19952f7ac3c39bd55d46b7cb84f823c406107bbdb52b9f6590d42640ada065820768fc74a9efb8f7719d2ceaefa0429cb0edd6636850ca5273516237fca0aa60ca0a909440afd8d21b76ea65bbc5bcd0149e073808e98b47b5f9daa6b569fd0619030f29190949d8450291727140e8ceba70875c9011413dccabbf775b6031eb2445a3e553e2fd891bf6794c6cc1a9da968031e42d089be058f1954519dc1bd1fed9e821fe2683f04e0936000dc9536f2c7292d0223dddb727623fd7dae3328a2fa343ce35935ad464bcd7c75b4478fce394b8b910b28b5f00001e71f1b922e45bf75f25f75cd02bb64cc10219f208f80f46c433dcffe5e07f64e96827b4eede19ce3173829a875d504ab2dc27c89af61784aca660222ce51b448368d015ef1bb4c14ae9c0966b1260a999cc2cb361853a1361778fa5903fa2f436c7a14862db3cd8032b1627b516efb1013c7ef502f5a8e5372f923cd04c907d2a9aff00d8aa51d6ed7e83336538905db01e77fcde29e155c5fab39ea1009bedcb6e67ea4243da2b7421235a5209b9b6f883bd257d92985edc966c4471ce32a069e9bbed242fd4e9e12a0ea3e1a153179c2df2df8c20123c85ca9d75f6cf6dfe702ea4b00eb036bc74c6aaba121fbeb32cc0cba077e88de9e9fa3bb349fb12fc9f64075e1059724cfe47ae7c738b3a1bc061f2bc43c0647760fe459c8009f4a7590ef18d18ec1c6493a330e713c49d4e7ceda4ea10b17a6feed9eb62c6f7eac1b59bda5afbc351e0d959ce095a3ae361a95e303d739a00bf698d01e169ca97efb8e15d0ec19db87ca290dc5a5710038fa120d13c3f782ca5ca312461145f284e5a400ed48c1db8c3b88d330100cebfb6b8ba9d138750a7dc8c2100328fc4941dc04704fa07ca065a79a4aab08a41cacf119d11d24d8ebd7f7b41968d378c504d7c26acb145af5b4d27d0764adce416019be1401b3b498df8a2e3e929c99117a2044bdfa52d64973c02c54e3634f1222912bcab1a044e268e29afbfb0c7b810d0916bb8bb4d7ecb607bb7ce1ddb2beae665ccde1117737c27b521db6f92898dfcc21b2f9881c9bd89c0f1ed025020252d7a87930eaacf77cce2e2b50a1457202b5ff8ef858afd32bf1f49c05fa58c11086900cc3270fd609a98c369ab7bbb5faba7a534fa0305f6b212cf4de5d9b0ff614c9602fe93799b46547f17426a6162398117cdf5866d6fa51980282c0fdc74ffaa14fc8e8b400c8abd4eb07d8d77aaccca431beff1d7108228e3ce628ecf26f5b544bfef043db8828477dbe66e0ba393190e495b91f7c7eb49f48a02716e5d5c247fabef60b32ea76da3cc1cac1b17d4b92326e1eecacceee3ee32bb80358af9af6a90710385e221b75423cf7a04b24e9cec4c32979f90710d8d715c532909d0f6a7c7b87b26e973e924a9ebfc9d84c57eb1308be01395570fa16ebafe69054de25e823a9f8e0635bba18ea9bbf671e360c610c43e5bf57df4eb10f4b3b69512e809e3626629f9ebe897dee61100a83a9d222af069274c8e3b7fe61b11538ba1e2d475f116f22215fe9bebb3d387030916e64284b8de5296046046ede4dfe7769f321880831707f0336e52b80f8b33406592b56fc75446da31d60e573fe442dcbe76eb7c29e57cbbd1af165339ec0c315293dfe41658ae5e7a59b8dd54caf96a83321043d4ec0145b660a7ee2bf21049a6c50314dcaa58af54eca3a0a762a2431b977c73fcd5a1aa5e1f5a365dbf6bded2d54b384d9f2bd7ba305598256e06e53571ce5a799230a93bead7d6e286118ac579477a209e7b0c0cc43bbccb7d86ca385d793468105c57eba3217947c1a52f5bbf569128e8d8cb2be127d8777a145835cb3b5957d7176c250fc38be8ec7ac6505c01482ffa224996987e87149f161010a50d1ba94593bee138662e423fcd702914c45e02db6abcacdadeda3e3a1c4cca54d1b42e5fd2fa087f11486bd8a0b1af696b3b82f06b6f49bdc4732bb3eba3f4182cf2756d97c1cdda459be3c1260ccc0164379d83a84fa8b779715906b38ee1aa2df195a941d47601aec058ddc0faa64fe4ea671573cc00471dc7eed0b3e0532660cf177fbd461895ca2d3d2953d961bad2a2fd2507c131362b86de8e2bab2aca18467fa1f5af2498ff370e465651f9fe0bdeef0f90a4586afdf92d7e9d6ffc8dc45d2ca8e611e40dc192a2839e1a455d58c2c1488e50a37b5c658f2acd757155c062ffc14abbb4d89669fa541b0e0745e67ef016eec5903826a8d579f946d1212aaf434a756be9e4adc990ea94ddb732cb6657ab17b5e9e06b9d52482dd806eb67352d25f7493a0fa827730289cbeddccc0bbebbb4dc45c3e286a699d571bb225e142aa11bb0dddf0495498d64ed5ec75e380a34340aa2ad6e5a7c05986dfb259e33ae4bdbf56ace2040a6c9b4adf3757757e50a74d01f1ea8a99c065eeec5022ffde8bc74094c326121794b446959c78a2fc81c7aa3d4c0d539d40fe768a9155bda614b279c4a240193fece9df16f24b8e6fae8d6d3370e89b554b16c155141681882d735846d2cc8ba89da1595b93a162843e5aae3a570c77b74c208199fc9dc1c87147bbe7e1785113fb16013c71bcc532dd11c5924e9415613c51f199d3bcdabc788f77d3c4fee7c2f4f2f45578cdce4fa46e8a279564999782e0c68e24fe4d669723415ad2926b3c59210a329b5dadceda753524dc5c4aeed48740e555e37bdb59da2ed1985fb494365703bf93d8496acda1fdf18347c343caf50affbb5f0345aa7e2cd5c0ff5bf74d05cf5110266152e30556ed5f307057f604e5d03792b9535cb1a2b9bfdc7afb85829c7b545ca1e134d0aae44b9b396a0bfa8e3ab177f2768a109abc3c900f532e544717783009d0fc0753f7db2767147d96a0a31a072a7975ce57326b2e9af01c54c70c279571bcc1851be73842048a86c14d3c37a301238306e6affb08828e0ad36204d841fd62d07282905577587dc7b6cf6d7245b6544a1936ed1defb05728db5298d3bd39d149459f31516d8e8860da81d8831a25b0977bdbb73c9c71fba79d1d6e596f3f28d7864ba3d93758d68f793fac03e663723a99d02954f7b7874ec4fb9daf08c6fa524a8fd199ec5459a8702defd859912c6d7addc4e613b881d60b12c69094b282932f505664197651310420136177dcfcf93ba5d5ccac2acc4ba26a6610b6c2f3fdde9d96d5309409894f8a5dba051b6ede5b4436336f79331d9ed67c05236c34de24ec3d2e1890b54d9fd47856d207ec61e69b5d3e084edfdd2ec2eaeb85e77b261caeae988878f122f8b78657b1c12f41f0e92ecb584959d36697baf8324a45bef71dc808e9d7c17fd4202278dddd480b8bb3f061a2340f7eff4ad1532fd2c4ef55a6b51104755eefd2eeb969613576fa18b38f8a622c3e315f2a25ed9c318f947694b5ea7886efa60e661f48ba2056c52e74961e95192e9f41f51bef7906283c29fcd2021956f5f4afa2d566becb7a429e0910cee38300054c2e7bfa10ca37a92464ffcd6d347e029349096cc38ebd20bd6fc3c3d3ad3924a1428e0d39fc8db1303807a8107d14085d34b9a5ce08126182a7b235da8cd7f74a7ebd6def5031eb32d019ed3c66b3f6c3911a1d0032b1eb48307e4a15cf2959617b86a0fdd7c44b2a3fd188e14c0a0abf12fec46d215b0a169aabd0e3edf8e6db66a07a508c751ee7527c54ef643e06aea7cc28e33839f7554b73e71b99dac78d5b826acbe0c9f758c2ecddaac9c57229133bd756f35225575a1c1197219d54f2ee15f32c179595a4d6a224c2ca1185059fbe1780d26dbf6282bb19df2a2661550f0456f4384586ba8e526168712872225e378d0f2603edadde3061a9271ac4b5db912a61f40e9f9ff34cef3397d92924be733ef2ef960536bdbe0ad9438bf2134971f8748bdc41e1568fbb0cc7eb5370c3cf9df1165bbc3db783cb83803250ee722557c2989730d83b30a3dd6c6e8fa68231d512518b80c18bc8177e14d404f59f86520c9a0b175df8ffd516ea3e9ad1c4ab78e177f26d41892432556ccb051bbb88f7b72befbb49cf97941b2abd65e8146292c6a6546f122fcbaee8c2e83d9ac7fbed9205ecfae6e22b53c3636d958e7a8ca58938081e4c8d939a10e4b3c616ff08e062c073303bf872d3e302b82b10569738bc940df136a96cab6cf4b2af150aa97ba9c7281321149c6dd448582974d068d4d987a41de207fd227271cc49406c25fe867500ddd19fd73bc9bd0a8e984536a678f0c2c6940355bdb7fac1623deee3da317c4e89fadf668e5499a71a94a45795dbe5d97d3fecadf15161ea518c9c08f2b1d9f40c25759213763c1c1c5f6a77fa03a577523a587c8351734b52e58fd2fb9dc3a73fec6279d062143ffaef9ba998c370c075966b6ec1c333be9bfce9b88b39cd3e17f76b6b115de56023082636daab491327a8795bd6dfb22f261b971d9955c70b2eb4050a232f00806d7ca2337107c002d7c09ae49eac21a0a4c2f40c2c40b760fd944a90572a84d12d35e3ee3d3e809e665150e1306d88bea8e8590846b3aec009122227b432835ec78e98233ad791bbca55342ce0b00c2e35594c4a5c9422096b807826a0a5f1a05ab1d3a107b0f62ddf743339252a3371387c1d973a929c6e70f9b81759b773fc750da47105d00278c57ead0a1bb1cbd8a4b9735b2c210a34f6d3cec69df096e1ce2f7e7e486770c202a144b3f5e73cd8e3a9eba7f2a0958f202ac72aaeb9c24f82e2a95e17799016d236b217fa2741e5ffc54d1fec7932d6cd98969286724c6670cf98e15af95df1b51d37ededffdea8adfbac49ee8e5ae9cf5fc9371d61a63085949f60af910b75261330635e48cd1b06769cea03cc1dff22a66c317fd98c8e848302392612dcd2706c17f95b68fe9a0ad036e90393c244085e3ecb83d8a5153a7e2fb90c4d787f6b0cac98786e4f883758f5fd29d8662d56809787d3d53a9d760eb6adfeb1e3972bc9e253f840f130ade60fa4f1eb854121204a242edde5811d858d02f1b4efaec9f34d405d9e33b10566c8557212ac69d45e8ef7aba810e22d1bb046ce41418550d80f2d1f695d73f93ecd19475080579ffd8ccfcffcee860551be78ac737fd4fe74b1235fa2cc6be12c6a4aacf0b50e7c09644b0e3d5479798e2d7b80d8f3af3c0c27b7b51839be2f7ee25b0f13ecca792196d6610d9c171b53af10cd43d2cbcb38245757b376e8d61365e7669bd4fc32fa88531503a9064632a5efd6db0ab515544a226a5acc3c33bf195fa5545a4d562cefaab5eb841ba22fd328694002f127bb2d10b9bc36b7005cb4fe567d28bc4f2701915ff74dbcf671b16a2316fda1cb846ccbf10bd6f5580aa7d9f3a286a52e68193f49e2d8601a6f10c408ee912a2dccaa2c872d691ca534a7130d13a30c9ae58858e50098bf257d38f2af2f833c1caab3acb7d9c4fb332cc38b1385550eb43332ad02b47137e987830350489af4f0144eb7d8598c8675bb1a822c77df6c3d9816569ecc6c242c70f28ebeee1a2f4ae681cf19834b468e86a5ea95e175447083a02ac9ec996fc2e34faf80f0ecfcc9802a46e91e00c97d4d8b648a3c87a2f0792a0c8a69c8e16b8dc6d73ea58fc6cdd54c6b6ab448a902599e9bbeaffa8d3c13da191620009c80d2e5b2521f348373d6557e25c0fad08885cd45a6749fddb2c5a19d7f68879cdd22d1f4d599e25bbe4f29fbef6fa9807e3a6b09b0354f8d76a00962684d8809b88d0b08c6eb9a27c6802591981dbbc2b1ae5b2de4d62fde504f10325819637c619d2d636a95772102987e49163cb21741725d041a50f585772391cd851fc0eeccb42a60c17df98734a27ba7de6f2f038692f52d8af68573199ddb064901cbad6cd89ffd2b44bcc65ca494eb0e9ba457ef6b1cf1a6dbd316c644cafb714436f4561089cbfb53cd87983f950bd311623236037dc92f7a1cd7c0117254fbe31f4b56ebb914eea9981e17e966d270bf6eaa4b4b28b0dd2db1a9198b9b9185a1ab27c56d322ac9402c13c2b9f28ff0f1e24c6718818a43deee41a12abe557fed29d21af1a201ef971675e708666939a5e4bfde4d73cbc5888604260fa9c85652b7ea8e944275e4ea5623964a3f4546e7968dd7b723332f9f9a6440341ecd0b4eda55313ccfb9e623279a1678eb55c56df603d79d4e53d7aeec925bccfca09fae8741bd809c96dfb9816db06bbdfc894081af8a59ef29c7dedc87c7b940b31c139492fb9c6c4f266d9398356be2f86869f09022a1a409df27c54caed78b3dfc13c2549b0e5c0292ef7429c779dc91f9e0d218cafa037805b7a4f009736450b05417902dddb15d13042e27753dcef437b4aa029995fe02b7393294b2ec98cf094311819fe79a9c1de773fbe220b148e2add9b648650c5522aa810a7d3e85aacca8e685d92f3ffa654d0ca81832cee47e7fcb3cc80d10c2a87f61fc16aaf120a84948427035d9434cb413d6605ebd3827e95c83e4cf79da375ab4f8ed6b527ec6a1f1f580940e409c5d55daba9606704d6ae669d293dbc3eaf3c7fab234a8e2d1588402bbae7890ec658318ee17984ea4ad5c622c3443243971bc4ec0fc1689ddc2681d08cb6fc5f1f539ccae465bf7e23fdcbb3ef8f53b5f641c3698a5fb454506015f3b5e3e63d36e5079672d7a6d2dc3d8dc17bd37871ab37f2fc101f9c26dffc4565f7467dd3ec426ab40f3d813f457667fa56c9d3cab5daf0b2b9a819c5bff16153721095dbee92eb1f2b0a2183f9a697f4eaa1c7c16813f955cf7da14b782ed9da490f3425431a4d967a3e65f81d214128301ed3f3fb608b03855b6398edfe10f7e0c44fc5e4e9f3edcf2300684065c527644d3501ae98c875213188c0fc03ea393982237f6aae23f512150162c2b56162ebef9edf7203bcfe7e1aef1cdc95ec8e31cbf875f59332ad3cf915d0b604a51e80e4e14844e22697774a18efef7293fdd98c30e5e2c226600223481fc77222c73ec5e9172a3ae297f315230d362bb677271998e903a4a79e2bd95e40c125dd122012f92173fbc64628462c0193daf250eec6884c1ed029c775ccf1560c4158ae4e88e13b8b6fc692408b332981198e31ac284033a68bcba3b7bcfb1a8419422150af12268149ce2f5233f664a239b3929a825fd395b18692a5b208fce9af254b04ed4675ddafe86ea77cbbcf5e5d728bef281c2d6df645603de62a132356f7280107b6fa455441e90d007280c537f7abf76885fabadf9e2f651aa4a8954639d3ad83af8afb05966b830f23483dc295d20a43b7a6cdaaf5c3f6eb54d02673f1f560a2b0c238ba54a72226474cf703d99b9e6ce6db739beaef67652754d4b50ca1f1c7f95ef9fa9c11867fe5bf195aa8b72a533498ba8b4925d63ab7727d7ad2e70de54227b311056d42f38d42b00a2507daf0813243dabf607d6f309d3f6f9897058ca02e8c4e402b74e6a3d485aac60a00a2033978f7fad0ad9f89a7ecdfa3b975e5b28a6c039cf6eb50e6893169ae4d07eda366958096373a22f85b6503b4b99d680e596271f344d2c1f57b11b5cefdb70e4315a71003a2e3dd95e96002e886188edf2b6a4c21e651e5a740008a8310268b275760005b14839614058b1cf7e99d6728e4ff1b526e0d52adeabf5fccd528e6bdc5331a63826b5c25a4ee9f1d91a3e91d310d9496f2bff160b23571274716ff53e955d8c8e465e2dc390d19cc989f6a29d5fc7f4ae44a572a0f42206837ea2d6b4e494a037b3f410592573bd300383594775bc10c7baaa6574137fdf2930f7be673fb491c78ce5edf6940059d66d5169df3ac2ff7ec2c418563600640b0815c82f3d3f77440bbb8636d4f485be010cb4cff545f8b76b7cdfbb468635265379309a987e26448098e7cc335b6cee2b7e681b8bc1aa8438207746897c9e3eb74e33beeb38ae7cc247e28aff1392f4ea308a3dbb85968f85120d6333a0f12860a1683a77652d5bcd79ace4dc8ebeb165309bacf072b8b44d10d1649483b2151747ec59fd7a3d6781c7c1bd1f32b83fcc462dee3ba2c84bf3a0b0510ea90f2ae9deee8ef133a67385d5f96346582e4652120f5a3dc0a3332499a9586137cc7cb4033a8730df9a18c1e6fcee7a806fe7f741d783de5691c35259e691b1d7d14afe5e4687b1d44dd9a709459d8ddc8eecd6f833a1f0f34970d75f775cc3af647d73da06299376df6309afde462f19682e15b81172ee61b39b556bd0790505e2313d4f9ed2162d8040683692632cd559182260529e53a184ce304b820c581ff8a923ec283a789a1a312d27cb3375342717e79e8f5c93dbadf74c98fa02ed1b7706f2e5ffb1beb8cbecd9562fc7c085d7e67b96b8298a52327bf4b6feae6455f48575dd352db143a63148a6da9b55057353a48e5c379deb5b68552cfdb45714ce1d23ad72fdd1a788537650a47cf4593f0abbf174ac34a7366f1e00508c4d4d825c33f1b29d9592633d353b827041819f03cefe2f4bda689e1995060b2fc1e3204a8d78906d523439d03109bde80afde27bba78c1b54aaefaaf4a450ff0cfe6ef4297a1d139475e352a53785a1311cd9f4e2f03dad7e3f73f4f0c797bd0cd66379acd29d1be635babf7cc5437fe41ef572ef1e72237278bed1bba601260dbed8b6b88497d56070973c9900f2987beb8ea9b7ab1bb36748898de4dcba93d1118b603f671be5f5ffb7a0f4ac272fcae1415db3480d8be1a599c7bcc253ee5f17898232ce45f3e0eb40c075f63090c9816689a011817724635fbdb504ecc6bbce244a2fdb3d85b902f21c41648e0c086b352261fb26901cdcf8a1a82c2ac35edea455f2a9368b54e0c580c2fda7c091b1e0046a22bdc387ca3c723b18729a967070e16c24a550a0178f926a05bb20d1bc63af1e1bafeffac370c0be281bba7093eb486160f8d1334ccc40cff197383b61e6b2d104fc40be4ea4957bf8513c532f044fd15f3a1bad0d2dc2c5f9cab419118af964301e58af9711d94c0b8aaa7098ba561754ea9092ad3d6e7e190af973c35a3431e42c9343208421a0d8a474b004f3d92463c8c475fee1e6081b5209e072aad1551c606a008da0d6da40c82dd150bfbe9464733f9376cdf2c9d741a180113d63ae7cfacf9a7e98e33b314b6c8af7450480adf9abd00515b1b0775e7fdf82bb78f8c82327ace9f01c0c4c1dfcc4d0cb31121f65acd7e57ab39d2d3fb27278076252e6e330f2d04d5ce3ab2e068ac081d2edb82b76689cf2c71a7ec508f8b784776fda6e17d1b9dd000c8770b2a698da124b076b1e111900610b00d7cc7c74ef8bc723442821fcd9f11b7c1564141754e85d8177d709b3d49f882d6a28056e1e360f0a468f5cbccf44faf190352f9732c4eeb0647d6f66cfdbb847b9b082585ab8a1d320fecf688eed543138dd01b5c508b0fbab5e3cdeb7b2f6bf191acaffd7e68b4029c68a0bb23696038b2ec3ba73021922a225805b48bfdac0e310d419391fe8ef97147ea711063ae72161a23ff076fc666e7043876bcd71c579bbc457998fc4db3b1bc7ff3d295fde83556d1384c0061b0c9eaefc2b9b44721087fdea6c11aeacc373486aaf731f5eaac4c39af576e91865330cfb09d930dd05fb18704bf3126d209a05183730b0803061b7d54a42c0b83281f30bc89922c518b3ec3965a0fe442a006fe2684b06f069732ec7ac1f242f0ae6823dbaeba6b8da7b71a6c5a8bcc28563e435ea7d84dc852764d9f15bae1305abb3d23b99abf4325e43824d1c5a6e66c4d22607459878ee36ca42aba127c1f92386d47cf6a85b7870ad1c63442a4824f5652817c99cebfe17569ad95398d22cb6cd3d3d59536d7c26ec72cb28e7151c8fe3188a7d8eb9d0c99cbc0e468b1566944582ae30faa182c85bcfef0d5d02349ba2f2b4d11c8c0c40205c9d82865784e5cc2723114004b520ecd650b930a7a09436de1a723698d37bcbe073c796294a1c14b802ea2c85f6d407ab3f382872ece71bfb37379f737f868062caa6c909ee7c84c9d769b9f305c5bf64ae106df48de77884b5eb229a6db972b140283bde941ac321d6a8270bb49f8ca7e16643a3938ecaea058a4047aeac23b90b351c7fb66502a70d04405c0615c7cde22a7711a3cbf2003c77a5bd33f619ec9fb19856f5066ec8a862ba2fa6317f5ed790fdba375b1a7ab17933fb281d8006ee374c1530fbcc034874c282d8fd7acc3a01a8ace5a1d5e4ac8ae06fc51d7797534dafdfa3c36d5845825513f48b7eed08b8ef7273f853d564a1a2f72f9b05c0ffd305b8674d34c6ec69a54deb65646aa62daa5a7e9cc6085ab2ff3d6da49dc15f32a6c8c72dd8a40aa6bf2af27ed63b9024b8821bd4eca6e06fc1cadee67bf0682f8dbbc99e603072a0b4b28e0be220fe7bd9c46cf071ac839ac08394194b32a3d3b8c628d6290633df09e6d1de20cea1f2dc136d5a09632f4b26ed2f0d12b080564ddacc2e77146349f5522cc8cdc7e659a55e333a6383b83f8a9fc09dae78dc12373d40e78ac4b4d35e648cdaf15850517e095254afc9c257c109771e6d2d73b960b73967c54421862672139849ca96e8a176305748814a2fb5489b7f7c2b94bc413600e016943f40adb8790e8bf7c077eb48ce2f3b36a6ca610add0ec1e0fe578c518a479072d4a001a16f60589d18795872f5d287c6918f0250244cb6f78ba530298fd3176ea2c4ab79c84ac9ed9ba5bea69758d96bf93ed9923254b92ea773408b0e5dfac5d0086d7f900aed8025c7fc3a73d9204f29610466bf0f7d2827760655bcd618f5a4d661aac5a5c24c6ade8f20b57a7ea1b693d8ba7082f0fa4c2b3b6827fa561914956fb7ced4f2b844afa337d3ece44bf7a7a3c53fa38b125d796e5d7ca7a99d379f874af2b973b7f69362f93f853109235e1fbe6e02db4e144c5143266327babaddec54e1385e605bcf62c3626967ba46cd7","isRememberEnabled":true,"rememberDurationInDays":0,"staticryptSaltUniqueVariableName":"e58622878c5b4107a5c053c29b821537"};
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
