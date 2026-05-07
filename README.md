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

        
        const staticryptConfig = {"staticryptEncryptedMsgUniqueVariableName":"cbf36e95819dc4604ea6d5f0097289085cbdce18acd026321e7b8e1fa366cfe1161dd6c13b83778068e56a1f8568f816e8ff6624a679688589f067e37fb91dde4bc7918f60303c57dbff6456ce4a37db8cc1a88d253229af7c96c373d3f76c6de78dffaa582afc3fa342fef114ff3360f8b5406a2888bca751643eb04012bf1e71a1ab701100a4166e0f7c8c85444955c2690e38e9721d8e4bc78f46edbeeab030115c7610a5f6173bb326c5c0f66c6c5458945d7b017dd3022dde479e5a9f1f9fe30fc3981b04788877e7f9f50d1645fd776e02e1b997ac561f841176a8218a0778b2a1185990280c6d0b1060a75310fe24fb93a0b9d4e1f636a86715a81ac85ed3c4a9e35e65665f414ee780d27e3458396e91469834caede51a6cc1b7715d0d2d9cf8c9f701db4b6d00287afcb14963ad8ea1a3de1c4b6ef0381a1b6c02ef7f47869019b168a2a7683772dd234625af8ed603af3bc68a5f9f5b5c10aa00d931713004c50db58fc6f4c2dbe4d7b4e074ffaf6288b2157ecb96116717b0f821f83df9e6b7ab6ed2bca90e637bd520829b84ba96356808ca3bf40af2a89052fe037797d56154a35f3a38708b2cbac76c1846e55b0f3a76587ddb3aa81e18cdf939b29c43b280fe4dfccdc44c0fec94ca439c4e3bfe846863cd97de0c836d86df83de4e8da8324458bb63b57a08b2c5c4f79c80db2711a35250bfedc8d14e951da63f4be8c770f7a956cc21e07c10453ec40a05e4aba3b8f1a712bb603c5dd9d89b7b4a7f54ba051f45707aa889bce795ad24c3d49ef9084f25ca9c3c5a285db744b75478db8cd440324b3a31914ef179044e00f9a873f22227c80b5a1876abe20b7bfef3e0e986353ec79472a481e858a12d949cc198aa33591d97e365675b742c52c11e590ffd15e543f0c63efa78749a1531583ee82de1747744dbf0f5dde038d212c49633b4b83bc00a26ece90cd2e53ddfe469bc17924052956e12d05ca584c9ce991d4bd960b6e983f81ef619154141e2c55cbe686d15b45caaf4153157cf919a1abe94865f5286f68c0e445ba65f90b7aff72376b642df232afc5be44af033914919f129caa0530f09caf45ba6a4b230aea4dee32b1814ff5efed60562aed0d0ea334934a921bfa213b3a9285b18c1b1e145e3603427555ff6802c1b4b2352caf1c2fee23189fdbffde8b6f8a6a9159c512c832e5330fe6a21dfc08a4e935fb9781d5aa45228af524a14e5b5b296d7ff3cd57894d32be0689beaa81be29800cc560d3bd35589a1ee3e00814e227a477a50d8bf6a763c43ddcc11e6a42a5b1b79bbb9301bb0e35b15d9db422b8b985fb267510727d7c47768ca23a0bdaef282227c1f32a265656316eb6a9a213d17b40a669fe5a023af806277850072e2511aa6e74399c87a3ec2e5f4e38a1033eda47786f2a6527fb1fbc8d961a09e33a322f37d9bc7b6542d17eeccb7daae9d4a14b49716a85ab308d05f40f5841994a350dc1c8600bf98a888d7ba4ad81eaa665829826e34cd6388273a19255bf773df3125c9292602c7834cb97407cec802765ca7fcb154c100009572ba6850ae234c119ca01bdec26afddbd5c3803cc8b8419b9437bebd512782cf1aa7925d508b5e2b466b78688e907c21e1831dc6f6675e699506066d06fb846e3c02c44eb2dcbccddfcb790fb2ea259eab65495d3abc067156d2a673e49cb9802b34aaa8e84d54e4a939e5f6259699d0a64a9f53eae337966f0eb4012aeed7be81364dac5b69f5845e626adadf2b725ef5eb4c4fac84587b3af1744334f955c85ecfe6cc97a9dd1d5366960dcf6a431ce344452900dec9d0b39ded008766a2d85b74b444a90255633695c40293d4f6522c7aeb73e20f8284ddec4cc4405c7ea3d0850c61c9a607a2a5a6fd34090baf5b76ae26b2faf9a21da4e7d9bfcc504cd77031c59e83643ca56eaa4583def6139986273cb687f28a6cae5c73a70e302d3db36d0fe7cfe698d30c5fbf0225a7d791a52c88049011ee17f230fb4b969a7cfa9aed923975b01c81b8f8615f33811fd8b7b374a6466adf3deb054ee36c8357119e9830105a1d9af731d2f44e9473d533272a0600f325d44f7d29a67d88087a5ebd7433c1c30a29ebefd79a9e7a24ff0f0cfc48a91b4ba6263ae51f3dae026652b97f9a59647727955a9f4f64c911f2b6f131b582b34e63e3f3deb01377eee67c39b5095d406f8cee415fe3a2d4cde7be4b424340a1ee1c19ffe400a758df458164ebc404e4bd8764ab1d832c7082dca01245a0347547c929fd314f43e704853ad87b639371df62846ab9b9a24afcbeac228552a49e68a4dcf54f1f1e3f578dbac8eb5101049c0bcf1f2f4186c5ccf0045a71bbca81e02a0910914daf3bbc6d80fa53d5e9ea61f11e5d82493e13a6000f995ec5e507ac8a778ef2b5f17d2b725d17daf26c2adf6a03956d3f3bd9e1c4670ef0ffc77514539ba07c3dfa200cf003a8a2a62bb796780d73090e5fbb6f324fcfe9db570b97edcf6c39ce7eec1e120ecc43ad37b9d4bb2cbf0efaf1062d233fa3eda96c518f8dd41844e0b9e9b7e73fa69965faa97959f2c85a42ce5cbe6617b6357e783406e7c583f2c4b699989e7fc6ba257956f0e77691638c9ee29130bc32466a8188394f98f3b5456289018f23083f56c3abccb2484b9283021aa4313e97771b43cfeaf8401720fe5339684bee1cc7fdb223e66e2defb99a63f2c0fbd1fd980a3bd0436a3819519c09b33bfbb4525f3370d993d943123d5baf395939b0f3e1a84b660a50ac21d81a758b4e3dd27b140f26f3a87a3c9f6c88c1ec3db721cee9ff9bc658875d7bac683665b77b9b06666ba6f03ed30c11f274850b5104e2a6173b0298295797587dddb36e1ad2b5379d42e1802253054975176f8b0f7450b5a1e7e593e6013ad0ab608b43ef2369543bf74af18a223ca3df28a31fa5eca7200e3bb56a67f73a492510eed3ab523b2cdab89ba8a776d0c7654792a4a68cdac83ae8f21bbed205db0bf1afc41f1fb0e28905667fa0b07c955d38eb694852c31074b24f3b5300c8e49284ee8e2e5eab3cb62ebdda749a7c751c92eb819deb7a5d520cc3e3ca52f306c0460528d905407e743c8f0c3ebe45c8874b01cd65a3801629466a744f7b06dc060f09157c3bc9e592dc550f33371a1a5a7c474ff4fd87c80866b4d63c593117dc0d6a9f6b43fd01f544fa722e5e3b9160107430df435e9b271874ac66359c4cfdb6df54006daefe5e6e23e4e015d3b2116ea1d7a61183073205849708783e5ae12c3391cf4c384d9a654be0ad509a9a4cdf51278fc3da968920626f0d1f39410f722350fc4289746ae42bf867f6c0829fc956d70ec0aee1e5d8cf5fa49be5733a725df9fb0212561e292ed8f6b5b2aaabf338e0f9f20a5d6e7e10fa71c7517051b47bfda933c8836b2eaa6b5912126b1a56dace816a2fb314c609bbf9dbb3e369de43519434ad7f765616d2306b8bc728fcbbfbfa11db1fe20919d5bae91cc70f0a7356be23ef60188b1e98a5018bf9bd6c1bc04e2e266020f6ac5395c5c74c54b77d41c0fd3dc6b4d26220972fbd8d8c965482307c22aae8f886cf5d31c8f1ee2bd6e6d898c6bc4f811c156b8cd037cf4c3aec5d9f0a26422ca742c570034d4d62c3fb1887945be846ba41edafd4208de23a7dc34d5664a4ccc94b75fe980f8042329df383e08aab739562eecd1ebb09e1f3976181a28ee83f2538b757db734c83381b18cd5a098b7a5efcce90827d09a11bfcf1fb864d6f1a68e55ffe9e1f187679d376c95cb88a186ded3362502335f1cf6711a3357cbc7709320cfb310eb26e5c0d05bb476825488bd426f4dab85c2b69dd9c7ba6afd334a76df9be3282efc4e583f73d9ddb9a4580368a1f3b7dab77e75ea3fe1e2293a7f2342220d249e93ae0559fab9eb07764ca0bd8cda986f44065500182e8b2519cb97ba65f8984309ecd6e36175465b6eba2d62fb29797574192e0fe42f1a354d284f5352be2ea523f584a7f103a0267e3817fa4fc352eafe9a4d3242a92876f415ee923ad864b148ec381313cd4dc09c391ea8f34f38f92b4a0be1bddcfa5a2b2e7ac3f15cbdb50dff32929a561cca6cc6441116fc4d02fdcf8d51a502c700e972ad646e443bdc836ea76f92633520614a58dbf45f0ff8e48543d082139aef62dc5d8141db7bbd2802d6cf7c8cacd66c33266680b107f1bb1d662759c05e2dfacdd2a3e1a8ba2c115a6a2b910c11aff8d10fe86eeb0ecd82c8f103cfbcb2bac3ffed90671a5fca12bd1ccd007abf3e75b6dfd66a10e37499d0a20c07da38cad1f649c35551f4db48e65d6313868872a6ab46a51bd71d02e3f7fca96f87d630737fc87de7403ac6f053caeee7cfcd925368730c6acf40774dd57a76f0d684fa23f2732dba02645dcd8bb6f5b2a5fdd1b9b53b6221ffc6b02728a91acee6d88f2d5de201f94389abc8501e9c72778b165356283327ec5b6056520a196463d47612291883b423661a326d65b28bf67f7d53b7bfab1aa17bc42bb3440387284fbe1444c03b886fdd7c3759de836c63fb41b3bf213bb9d7b52adcea10d5e7c8f4ce92a5dc687d5c92f5913d91100a6d24d3226c6463e333e1f9a6d41e1744a7478d2bd0a2a31e1a0ee331d216b7542d6c48f88ad9c5d72b30321bcf62675573f781949ca34de72be7d2d3161a643ea53c1733d6308a19606c208174dfac2dda3ab4f0932f371a53690555fee84ab9f89b46ddbd00c1bdc4c4f156cb31580a8038f426d5f280f74fa8d2569c4c96679873367427e64d7ce209b4e1011e12eebe41b3918599ff977d1ed633ed92a7e2dbbe0a384431b26fcea72e735c5112b7e02999386479e68afb07a49339cedbd302f4d20124c8a9dce3e1f10e634f0c95244a98fd4b06731a0c02383d14819a2ff88b1bb760d876617c5e1ed8d8c0a48530666cb786f59c8c34985bdf91c52e2be3762acfe645ef02fa4862d74022adf9d77428f8420738ffab9a87dab8f0cc3f959e496893f76cfb8810b90f70b252a8723d2647ac196f495e151fac4e61fd8bcfba9cbcacc93a6358e625249ec1c58e6a8d604379c7d1fdd46d35cc7a8a37fc437f4fb3c372a886155463452bca78e2a940080b8d806b35a0bbf367b2771ac1b0026b83e4dcf2f3d8af67746e508fbb6ace18ad6eaf9b0c22d5f6d323ce4788335501e03fe28425ae39015a76c13d8681f0bc62ff433041781f07bb34f14f34c3ba4809b9ea45d2c883d59ec5b723a3f198197be222712ebea50f4e3166b692d5060f7cc9bfe1b7f2cca49bb32fce5195a671e395317b52f6d93ce0d5442e38d9220b1c5a6f0ee9cfc683bc559e190c4d93102a77a6bdbefb594971921d3a802d7059028a405d642069852b40ec627e09c4d55112d01e445935cf01125e2b9d2d9abc2c0dcce5c41e9bd3329882a4d9ed91e45ac6378507e39b644688a229d9daf54a0320da8504e1d1df19d51d2532e951994b92558d9a1b4ba41bdb01322ab3e8c9d87d9f3eb1362d954c04b511cb7068d935274289170c88e5b0e685c200b803d9a5fb0a2c44c781d3621a06346bfcc8b1b5445d5d012533922afcbb3bc3b5436e6593b46a1df484c62358ad0cdd8ae54e21b4135e889e08df3a29423dab78f5cf24e08a4a5355f8aa2b5a7fc3a15ab3d64c7112a9e7f006d63922756a14f451d4dbdd30f23a15fa79cb1e258fba6814f960a051a41cd24434eabacdd710a088a12f6a50541efcc6ada1ae003a8385c24b4b1fbf475bff771b3a2a22092dd111dea430f85a8375faf06a5fe7e554bf40cd3218b05b5c1bc08ed7271335ce50f99d12d253f1daf76ab49cdada1e70a2dfde3f3fedf6a2e40994468a06c837a65135795d8fe37a389df01bef6d7c51d931988cc131d65df417411d64fc3ab678697c9528f0df9ac43024a7e0a01ceb147f0eaff0aef21ca8807d2a740b1a13797bc32d4f81db106a95ea9dfd45fbb51a505b5ace287ec11907e11da0f66800a900649b83738dcb1abd8d78647cd98fad967cde8cb8e9e633aceede25250375541b089675095a92e5cf753240c6de456dac3360695087be01bda9c95c13be81c89bb083ebc662318b7950d7292c298cb75a2c6ed599fa6308e85bb1d92ce9ab0a6dc9b209232f31911821daff2814cf31d63a0611889e65342c4a5008addbb86c3f7b378faf3a4db40745884dd5e80fa0877374e61e61addd0b47b4e6adfe4dcba6145b2aa20a1eb9f223573bdb2c9b41bd9ef5342540370709ff32f3051e8a4f4b77f23a69ed07f1ae1f4e1ed22ae8798963e4d58421cd131a5c5a0dca515c9d6d61986ef96afd4b5dfab6e47f7723ffac0e4cecca7af986ed5cd77fe0a9c2e77ccf2636a6a19d076670578c2667f879b1299bc721e909f71d2f5320ee7df6a53ddb99bdc5a98f76920231c36cc41c3743afb41814410cb03afb15462c473650e822edffe3382218e7f19af3280ba68b818240242fa2386edc2149466b450f6ee41d7160255a2040156f037a77df1626d0e12ecab04d1403f797831d8d39e08b1d0a119f0df1c70fdf71d4c3458494d5100a464860ad3f5d99ee21bc0938db75452b2abef1cd310e2b0c5dc2aabd2de4942572a8e3f650893f9c0844839db31fbd04524a5bcdf9c4e1b1e33da04860a46c9e214fdd94c738ba45ff0336f5301c3ff0ffb111afae3224dc35a909adf804c11a91e8057b83454221f0e9081e186a955c12e60a23af3d56a87402f078cc9f67d40a2c81966faba0ba5dba35059044e12ddfa758f6e5a03d03cdfcd86629c116bc869ea3b99de8d93cb77b3d5f080551f6068b6a9558ab2054df1c326e91056433db16501ac7252d4dd72402691364a18020090c58f3fcb9264148f15f6f4d8be57ae984314b83f894461944b33bd092ae0fadcb6d099faa5c26731f7ea064c1f7c47ca30a7101b0f3d98ea5a540fde6346e798114cecfe19ce68865654b1ee9c6846915e03385d922cafc56ae1865ffb3c2f7a57c1a5ce7f5d8ff107df9f6799b6a21b422693daeba63cb0c76de7ba2cfcfcef68ce2c1ba5efee33fd8189a8d214fddee9b7cd1a91e650b19281640ec36b4ea8b272d1a95f282b90a9aeb3b3f3289506b4b4b7ad8d502af095aca541085c513846f6ccb33f70ef696471c47733ad639af6916e371b19e5706e776e9981a263feb8541b408fbd187b9da60004b46f8ee5b6f6880dd0f6ee025533c6716ec86511aebb6418fa3c0eee5bcf14b6174f5e9878e1f2d9264bb4219f47235ffa7efaf9e45250deb300616c091aa59dac6441b28d0298d4d9ea078816f101df6fbfbf18771bcd70f30570d7ecee6b4e6c051cfd591bdf36151e11759c2159b4b6922fbf67998a4ce9670611801c62576a2d1054e0b9ec162db4c699439389d32e3742975aba05ff093f00220af59f4ad0b6df589f6fa5ba46a5a356011e7be86b349fba281ee851eeb68da41dce9c649ceebf12093c53fb1dac2928b27b77f58471bca5dfef028d6277c01e1a30854475aeebea3bd3eb5c7aa8c059e33b31fb2c35a0c0dbe363d02e2cd5fa5492857d261143246fc8ca7194301d73d208439c3b2809081930d0920ef7e16f945035b6137cfae6cb3496fa2f8ba3ee1397fac750009677cec3c5a6724adcd583349124a7fff7cfa81bb03e163acf3c68d44e97ac4f5322fe12733210a95ea08f96b0792a2e8e96d53ebc03af453653e4ac64d0d021dd1817e61073cc4df73966c4e35cd9b2273c06d0385de8a00ed0a213c00df9b1a6f5defe21dca4f1b67ba2d59a61b61e759fabfb1025c399b3b3e9d09e7577dee17475407973d5997d83c801c7fa80dd34ba38dd88bf64af337f9ba9e760038e475d13a183ca36f7f7053cf4d8b38c58c2b2d43bde298af8f3b2f6c09e98ec012c510299eeb81a9739b58506d9ea4608a572a08120a41d0d7cdb9f68e2f87f8137af778ee3467b33a6dccab49784f67d2d8b116e383504aba02cafd85d6f3dd422e89545aca9fbf6163b6ac9617555a637c462a8934c02b208c36a4cc1449a96c07b717a477df93167e3ae03cd79f53519f8c98f65461140432e3540b45d7d3565a30add3a6ac5337aefd7c7fc3824bdc7999b7798b47afbb7e2dd4ba962a3038afe59b85b4a0962998daf48dbaba31fceaba2eb722bb3a9aba26d11aacf495efcebdf60d59e294a1c50816483cee86becff4035555ab661aa09f0aabaf1be12e76d47352d34727e340d1f6066a7f467e69eca982106ae0d1b66b4597167140b27c88a5d26d374641a7d74acc0b7861e811b03cf8e5cad6c1a7523bce0ac6e8485868c022cd75c588b8dfe4c646139b20cf91522f0ddbf27c4fade553ee00e741e5d56581c7dc14fef8d7fd1ecc7fc3943c448aae996baeeaf4b8add57068f0912870a9951b1ef1cd277c7858fc3380cac0399898c46f267a42d5647974e7f53d6a44fa07c420cc88f6a1cd4dcf1c4b259b4e353de1d90a0de2d31b2eca488b5433c3b4ea1ffcf04b0cfa2d59211e58e154f2a18ba40a1ff36bcf9eef31e68ecfb7d2d5db15cb32e9dea1529d924244f608e022bf2481f323f21a5cc2be252034413e915c04d97e7085958145effc1feae1677045dbe529faf6c008d536ab39e5ecc5f4b2df4a90878ea1278de12cbafb1a35d0b4cff1cafed80d84ec25fa4294e0235575213ca891990b45ab5fbff9e2950d2e491a3c8e915c62814e5db31e81b751d6632d1be8e5c83f107dbd02d8d6f1b10a96ba2804e5c3871df8c19f4b599ae9ab06846ec553aede48dbd33d7800fdfd8b1bb5e2698d501308185f71a997850e9034349b2608d25078655d4b8f5dccfced5b95d88be7d26f4d55ada27972fb060a1d4573c6a2499b11c815674a16763f75dbbf33f1ebccd6f9950dd1cc7ac47e6f105a23e4cc8022123098274741642544c7b38dd735be7a6b3a3ec9b3d81b32f56b48488f715a9832f935ba9332d22d465c26a6088fe2d1124874f7587c4896db58a59b88658fa17dd69da76a430003a3643eb8fd377493092527c0935873867f71bdc472fb7f83a5f8bc896508086bfa86ee6fbf37b06c03ce3df8d7b79b800caf6fcfab59314fa30e2adac106a3ed96487299479387a83888cdd05f9e2ca7a906d10eead2a13e6b2ac89d23fce1094feb585a990760e42367694b557087abf23903d6b3ed11618b69ff98ae20d705f2d750df784a7d9441f0f914505f83aaf8d9ec1160b56a002b63a472da731735199debc6eb833b9f4aff748961964c2e01676c2456eafda95ba81bdd5dfe499221d1a53cbaead696987a2dd857db18c92a24917de8927627923d0edb1a38050f9ff8cd0e8dfd32b4b37f8dd099efb5628c7b145f1708c2ae7d0cae2d12ba523f25471feded94b48bfb9bb676dfc259168e3dbc31c9f0faac06c83f7250cdf04c13348e3c7ac9bdc58e969bf6c534abfb7d1a4da7af47f37762efd2c9e932ba4b85b9638b8d483d72667f434ffdcbd155f55f5810b71f29c7ac65d67bcbadbf2adb18e4289792e1015e6845f2ece085c3c2cc91c8c102801bb212451afd4750c99ed020e915f6b2230cbab5f081b5f6b0c9e057e4c5efcf47df2cda61293c25d180bb14b01585323eeb341afc2901af2ef2db6037f395f897a3f4ff08c801330193a82da5a62d1e7e8a1522f994f7e39168fd3b59072568dd211ab0c27cda2c2c49f4e8f34ba93497b39bc60c4fde78e1246b9da101f2d12350be52f711f97d03f31473d9dad78ee8d0bee447ab32b14064f5506b4a8d3472ff6d4a938e0bcc2699656bf339ecec7f95cd509c231cf1e207cf8386416144ddc4e8e49efa26072022c0068db880f5caae440e8f722066427f6c4bbd7c492966d3d093dbb590267c3fc057e074c1488b70b99f42f1448391556ae6f6cf5083d93ba6224cc90cfe8d6b49df2bd99281c8c9df96d8ffc495dc009af0ef1ad7f4ecb9d5589b3d212110e74a7c293aa222127dcc018317ac09ee313e73c482d3e57fc8df96416d360b2213d31ef6e7da7b4147a53bcab8ce5d8ee5fe86cf441356b727aaccdac6f88a64bc0cd9951602c8c55921512cfa658cdb565b46a40c3fd2c115e36521dec28c6ab28fad922683d20ce14b0864e5b4a4ed22ed71ba154d6bb17f55e14a8b26145486fa4eed744d494405b2414e33a2085caea7b0a54c8e630c96cb75c789e100f8ab23d37eb5be8af0fd7a47eb75a1323ef9938a5df905cc208a7d07411b60da95e5a75dd3f54dc2c266f6c1566ed2f286b8133cc6919bec1eb8a9a9d9051dc1072174e4da6c187d46ce3513bfe96b42a1cd71f5891de811d341f0baa5cbc971a0e1a28da64693b5fa0172793d5cf0098791ef867eaff38e4a24bd09ca614c2bd0b326440082507016d314442150f2334ac60fa8a2439e9eeb91f489375671486ddfedbe489f4236d4c032f64a64d2221062cb8e9a8386c9439fe37b76e8c5bcb0d58d8a95cd1553f6352b7658b8c2e45d082798b018afacd0e47c8631999b2d92d1b5172ef60069da9a0eedcc79ab8a1cdc29ab8b0a75853adf370b27d594df624cd5662c2112c5d0a4e10dfc87fdb21d62896504c3262eb53ffd387fca342430856cfd4fbec8e467ed55b606842528983332e77b073166d6db26172df8b4b672890cd884be13d46dcfab14b715a2d7161dbcf755abbf17959c231bbcdd71251ef5dfccd3ec5fd3884ff834f32de5cf03c008e81422e4425d77291de22c1390fa94cc17482c7ce8f006336d9a9ef1a9508bfc68c88fbeeac942adf257647131abf5e71149a598c8ab95e3c86743e81ac058d13742b5a50dbb5c0797d563b88d9ab6d2c9c16d660a2fd2474cf4e6da0d7767514aebbc9ee0bbb4f9655c89a67afdccd19d96a986668329c45bcded1693e76633b051215c4d2d6826b8b0b5894dcd8132c47737135e025549e2f0b74b352ced7ceb36366e57218c77865064dd86cad6845df96dd0d6955e14c0108e213a3af45a9607d48535e55a780bf42e875baf622230f34e979bb20a6258ac9b5975b61a5605f1ddb375891290bceaa19aff5f8a308033c285f48b302c5d97d2af93e0e7d80276facc8aa69d5d24e1689035e8959919f4d77507ce11cd37ffe38076f68a7fe49058f3cbdb986fb3160635e53089068160a4dd251e2088fd90da976e45d1a8c8d2afe7c01bd86c7f95f53bb1b2578669d0daff96d050ab0b5eaddceb51476224184a93e12f1d67c2a93792db60d84b3b6d5425d3bd4d5fa0d4d83079ad810e7ccf5f08bd15d2ceb1f3780510d1e615663e5b0cb7afaee082a44566d6099b5f9fd20f27dc508425e57a151cd3c0e0640a760080f4170db437243ec25d16f6ee71be939e0f6b5be13d50ec08015383ac8c6638c7d4dfa5d31eedd504ffba7fc2f1ca116700925f12b9589337fcaf3c4478b328b5d0dd162bb0e342bc763adfe8bf6c1ea7a66b4ca9615bb6147374954d8183361f7114c5d944b6ae09a0ca3c28d432e04bd2a83402b141ca6812fd1a9594558f698594d6270119f892df8164c55bccb8ba94064866b2f4b8b276789a34c8cf0786a1ce9d9921c5cd7cd0826fd7266fa6bcb03a22e5662cf72badd84a1d6bd669e9f85f204379084623f6b19a3d6a495b336e88b52e022e5507d1fd0402202c38a48d30fb5cdc74bdf1872efa8bc126a6f71f056235191472a98bd1ac776afa20e7720a29d505eba0b60d81c8081e9afdb88ba83edcb75915b5e7564e39bd4b5eab895fa746f6415e1b60b5b86b113c334b48330582bc7b7d50a8fad5709a6ebbcb3052984fa241517506b710f26e05ea23a3bf51bb340324ed4cc57b02b736366a7a8633627aaf685e763c23ed2b10a751d9da542802c7dcbf0e5a4e560f445691bc358e745b6c0af4b5a5cf29f09bbe3fd73c9cf7924dd70097c1f42e3fbe7d71d9aaae0caeda3bc90922b89b57741d90bc9d179533edcbfc7b64cedd867f5756ca9e7e6ed13ab3f439fed1ebdba7e75429c442aeb454713540882716881abff429184e2618ec961c90504fa172de0902de5d788c52eb3e35096d25054c6081b7b677c47bc20ee01953b67f44d8bff969064a072aabc3dd003d09975a2c4e1ef25c2825a806245d1bfeb9662013036ed8c0b4ec4a43139c31972c1fc3c3a4d3ed4d46e43cd0d4801971b6053dbb9a4c3289d2f15ca0177cdbcd8694e953ad7773faab7afe3ec2a7b296dabbe3257bdc8e408bb1ac585cdc4faf3539b795bc06f822c6971c3969d6d5d8535ff3d2f5fdc0c87409ccce9bd274ec787a6c7795cb47a86d6a01537971692daf25110784ee5676cd5d4d4e7e788797394a32ee52f50e32332d72ebd72deb70e0adfadfec6d82a8d40d95db9b98258c02d78acd7361dd7bb64d99005989efe7666010d61d60c87fd6828e099c6f4cb6fdf35f272250ff8b44e17f61b38a7e93f71b32005e8a5226dec93835fb147e64861719ed446479c3230d6f61245954102c05cb6439aed49855003f81869e98a51b95c00f525eb0b3bf4a45ac527924a63a06536fac914c8e654482fcec703065ae1280791abd947e3fe926d2de151ee0659eaa8fe140e9eb3bae8e76815397f9a492873723194bf9a734131a28b432e56de96d8792e2fa5d6c6f74112d455ae38c064890830e6d61c7023e6f28182d03bb4bb78311abe64c162af0916be622bfab465c5402d00d2aa5d52761968717bab4f62325902bc87aad59d10607baa75da7282f2d8f6ac22c6162161e0ec9e4372f5556050efc23f2c01e5e6a97225620ed6286d98a6493049cd5e55d5a87b1932c2fb0b02425802ec13b3ff2801884d2be1aaac23428d3c04139b0967ee5f3070d34d05405ed4cc37d7b80514b42bed4dd066ab39d3bd1cb2f36bcec0925c040f5db3c8808fedb8c9ec3129b1a9e654bbf6a34fede1a6d419d0fc693c63358b5dfcc21f1b05cb902ce9cb4020acc4fe50d411aeedab18b94d8c16531155a2f76ac09d86d782d4fc1a3ab22e949f6dfc2b1edcdd348ee8c1dcb339724241c08e8b69edb6f286b36736b1310199dad9eb69f9f4a069e7a155c010a6bf998d2d371a1d10eccc05ab2ef16a951f1cbc2c006a1a559668e8de2131622a0a06937887040df0ae650ce34223cb717939de2c4f31f423b3fcdd0ffcb102bd79e91bc6af31f16b05416700c4251868bf39bb8062deeadb7fbea74fa44834b09dcb8c9e7540e89eeca78b4435d45d859114d97e9648cc390f19d64c0392f25e624380e6e672f85427ec03b814e452d21ad1f781e55c6a2a252ee25ee87ef85912ec9c13de8aced225080baa2be9c1f2cf66c0bbe07f5b9ed7168cf2aa0b54c197a51adf59c40f57524442a60a4a2d31c7995f0edaed9a08f27ce48eb08a2778d6ca7f46dbb7e20220533269154d92e2d31cde623a68de85568713213970a46488213c787433382439c804b673b16379c4f9de68c3864d768fa1ef94378935306485365eab4cf108dc59b3215353e48067e0ba9b6efcfb1e6ef37715886332216034952b88f1a51b0bf0d163758f538267cd21864d1f282f5a436d2dfb388429427234a71fc794eea9afa37cde067b5ce43db94060a2b992093cb18b930712dd65604876186927c7a1d88fd17d183997ee32494965ebefc6dc6dd09aef390dbb94374345c80d7ec2a20404cc82664e24c6b35a6cb36f018738be42234d76e3670f58b4a5cb365f00e07cb78b233851cc1a3c6f8897b69d5d80c68f5aa8ad981077edb43d041581338739bfaf3c6ea0c6793146e245f205758afe55950db7c7fdacc645fdc36c4413f4921296d71e5aaee53955c49a6bca2ea8b5d904466238128e65d1eb581d5015081e9fb1a6a8fdd89554fb859a6da85259b495728e8ef995b220e142806702d51abc49bd3063f8fb3bf2f33aa7a2c980ecb8820610866fe459f0425582e0dc1d1bea2d96c03fe9115538455945d2145792875cac6663ebb3360571eb08ec8bee911eff5a8c9851b81dc194736d5f87e325903ceed8cc936e706ce942860bcd59d79076fa0154c8b3b7392fae5d5db47d4706312decb3e1e52c350e0b40b451e4886339dba2b662269a4a697d96740c7acfebc78db990fd7380d4d6bb74a0f317d41d280e48353d48a614291e5268671bfc1e739de5114a05c094bf66fe75174d7c0f109e56fd6ea93da94722d26ba09df53d259f2399fed154363ef806282e2753c33884cc8b58f7e6137866c8ba50e8abe1e1e452b92f224e5492ebb389a213ad263ef9ee9bb0d7112ff84834912b5805c4228034859e46405ad8c1555cd50506a4cbf9c962181d16752ab579255227311890a82afa768e0a1eedfe13e4897fa5406a127873061b42977bba9c60e31f5ef9ff4b9a914f639057eecff2179da526ccf6b521892621489ba057244d232035190154da63eb09618840ea983abbff42209887510e1aab48365ac08cdcfc8d772f0e4b798fa3cc609765608d6b9b6888c68f87b419b213519fcece0dac9d4c7db5a177c46c3d3f728c60c71f29395bc783fd3d814794f807415e94fb28fa3b6009253796fdd6fda2c238e89f8ff60b1e0a40113ca3ca513b52954c0ea36e50c4f4cd8514c2b8444e67baa27fb5f5d79c2ca8830262000ea6ba510ae5328d6e132a6e137e3309ee43fb98573e36a30b42de978b29e75248b07460cb0b3656796b7c07e5e00aff5f37f432ababb379126197c2a273e81e420b53284c068eaa12c9af9420ef70fd6b72c00630e689d5c2c063cfac224084ca953b5c9f49e4f58d09c78742d37827a8fa6fdcb1d067fe0ddff36d1d08962e21e03b2fc5100910dfca73b3f0252a3eb57436cdbe897b65963ebad4bceb96c0a608b3eaee57502f99c90f7a6415565e6e465c3ea31da057e6a920598b92a3dbe537477d9d15d26b91eebf7bd404cb09dda7072b99a676d1e4611be58264e06a0128784498226967432f98e5cb3504f77504f57dd7a58b1cecb7a639fa7064a9d80699f7a5225f5891b62a9193856df71ed30750ef6c279eb7d16cb74fb599c3e822d27dc7485ce3410c8a74e1df336a41362f5fac2498fdad8a36da13ebcfd28c37ec03ffb9d002e9e348cc6b2f58520fe27dfbaed70686dd600aeb6df8f5757559da3374ff3a4bafce59b9cf403c416653654b39f0e2ca66408297075ead709f0c726da8eed9f93515482e0c9ee88aa250abc232f052e924c8035bd4c5dc59a84b52d88e646e381bdd6307aa73e2d964bfee8ee87061e063009bf95246946f7e4078a9dd16c193f18c556932650389b579603a7e0a348f20f0bf8d43571e0135cc9116a638af1718c7b1cf4fdebb09e592e159fc63426a737c1f22a66f3963f34c2b2de7532367cdc0c28996b61db26aeef405df358fa965b6da4912b8193feca8730ab94d3094235b7e38f4f34c0671b172a5ae08c7fab59ef07b5ad574db3e8fc408532c3cecbff92cedae833cddf22ea51e911be0cc3e336743c7875b7a331ad21212ef0365c98a0f495d5951801b5b525e2c08a14b5a569fc7834370272792f2f6fba38c936f3ddfe2c43ba5f74045ebb118b65e0c172a105b57da16d2fcadec2493b791947981a8a705993912bef21997059ac72d7da332eb8754b596ebacd2b8c690695fab7ef7102905874e18ebc2b78aeee2d809a9ea5c75da1dee1b1228e8984a16195af9b2ac030ba3edea22793788bb359da374099d91f952ca901df2ce5596ccb15752a5c4f41ac4ea3898d635d711c9e23b22d1e207b90df6dc8e22939d9a3b8b1f82b463729ca06d4a830489fac5a2bd2f527196e5ca7bee3fb1224d05433e77e4949c82e8ace10625843c31614d77ba59b80ef0dda82dfe738cfaf81f56eecc9f202e46dea7d8004dc5fe1a9ca4dc3f48587fed1d6d6bb6bfa26804b8b5d8d88516cf8f29190a7ff55dabcffa07c40496ad0c58cc52de06cd6f6fdfcbe1339468ef9c0f6328db0adb12020ffad564b8a66be281968f83c033adf2b4b6eb79eeb221211088d1c5fce62a7988c2e76db1d4c6fe1cf88edb882a5a0bd4de39dac80d455a16ecd5bcf22eeaaba4bbe3a363a9ad55afd846563f531d8f08ca9db8e5efa4d18a9af266ab47ab07d5a9af6597d8c4d253be2ceeb7221a80b61656ed46221971e78af54de6f1bbd06f466fbd1baf91b03e40339ed00c287b49087a90dde2849a6854c05a9bae33e99b6bb377a5941ec4baf3de448dff2545eaa5016e7756b1b14536d3f9e8a6edb17cf5baaefcc7f25894d898d36e51e8bf71d5576229b7f8c572148eeb85c0a495cfda1edaeb1cbc48fc2b66b79b6d96939171fdad9994a13eede3e676efa03a1d92ba25aed9dee04ec11a45fdbda48c34cf7c937ba2c784d78ae19d28098d0b18d0d8850c97bb88a53e0d2a836fa91b5d58fddc0ecc7599edeadd71c8c0cfa08db28687466ea5a144cd1d2bc053597fc60b44f93a33b3cacf8030dc61e560dd3747311a7c509b77b8dc8588d1ee231bbcaecf7c64c7f91a4cbd2c8d388f39986720a1222dc615696f72e5bdca7799db18337e1a7feb614b759c31b9f523c92b6d5e5acb22d894ec1a5c4681491047001af7b7eb0058e4985ea1dddb3f5bfbe2684d34a0bb3c363fb3dec420c339f405c2a2086801edb7b74fb145274cb48fc167ce7ed9df62cb467527a2c8a6f77ae1e31057c6268ab554847548f87085d582a7fec6ad0fa76d9e232ac561ba41416ec3b2e42473c023a97046adb00f8ea9a352bc091f02c799e56be7936e1cbd5c5d5255224faa6140aa1bbe52a1a03218ed461908165bad1579edf55fec175eb62c0b10aef0436beb4aa8d172113ffbaca8f81a22884f66481cdd94b81789bcf0945d994bdda7fe39311a99c8dc0520e46443459a6aba0f6374c68debc64b5b403ff91e351dece0ae21c0a5895b1354cf5ae37fdfad674f529e525483eb7afbb7686e7dd70e63e30f40bb79ac7546516a5d0bd1d608ef417e51d8dc6769d6174bfeef04a9b96f46804d309434dfb02b03ea1901dc08c8c7f8b0b8b96babdfe6cc882705b26dbcbb6e80110100830e06df3e1dd375ea05e958cd7a181d3079a43bb152fadb90a6d5ef8c17da0221c8d4da4eae8f991883e21197f119318f10e2a16872ed40b162c4ecf392a72aad9d56f1070c09f73fccbfa7334f7b7c086ae5bb6586be6a50a89038535221e6b92a6e7946a8e429ca03319af80120d78dead3bbf9873af892db9aa0faad47ac8a3494871d3f2df6796337c6a4045e4b9cac3e0776fb66798f9f999f1dee76b51ed5113d8254d0055fd3bf21f3fdf573fb40ea5d1b1e77305c6ee464ce80b4733d8b9b87a45fa3887dbd78a7149ec0dcbee0245c546ef77f6d4a37136707f16d2aa6e80722d179e869c2dd594f70f473b4b96110449a8ca25163a4183ae8e8fcddb5b6631f277a5197cafb36668b723351616fb9a51fa1758aeb448bbe0bfe18ef1dec91a3d43f0bc0f879821d0f4a09d2c38450e5bfa2122af57204268f120b0afc5687917817d2f428cbc7e710027b563884dab64be927febed6372da9ab9fa74eff45d769f3e4b6e3c732bbad6f3da228b565e4f3a03bb9f6feab54f9d7e344108943e85affc99c24d65e18be4121a4377666263ef98e73ee5643ad4d4a8a02ba0def3062e8e00288fc2fc2c30df17586882c01f03cfe11ede97eee89aadfb04325f556997b78a93963e6718a9c228d342a864c2a36f3000e4d36a76287ca8def774a6ecb0fe2da755e63e0146b03f5692cec713aeb5c59971caf00396ba5da8d7186c71d7ffa6b93b2d6e220e2b992e210f568bb7dc17802278e0f871732ce407f301d65bdf25e8e850b1087becb6c8c09bd11dd0f5c979387e62ef4bd37f759f28b3b00be956522bdcf3437f8fa4d3f2d27203a33de2770a5cca5b0bb44effbf357ad6a30f9344fd31e8b32f36075950f1d3ab3c6b0c101ce83fb0a1726dcf2ac9e08b8702cde8b3ac08f0a90b3fe888076b523e6cc60eb935b715bd7d22c294cb365e4d7b61e26212715de2b53b4d0db50f38ccc90d82e8b6862a0054ebdeadfffd6e386c6e6cd77cf8056d29cdbb1ecf297640a998bbca5805ac42f7d0bd19e5da43aad7760a437b97e83b8b24186bf96e319aa23925ab357262cdd079f133c11d583ca3265ab3af894bbd0e2ad2690d650db1d81f2d9d9047c5920fedb1bdea27f4013f16e5afbda3e690fc437274a1e838107e365d8d74b42330a8d93bd2c3d800ebdc1afe3403b126b10ec08558d264757d37d5694bba65b608554383425978e34573f7f04068898df62403f3dfe1a5246f821615bcae0a5fde211d715dae1eb0ea07abf7242409feb1a7b503dd9e9fd27e95a7beca1a203204f6305f96743aba636fbeea40fdd0f7c60f89657f4d011bc9e8b3fc3f846efb52da266397c4b8fe7fbbb654883268dcb8dbe6361916e95e03d211140a068048de22d49b6cb31c3a02535d2a2a0d03a9507c6fd193c668edd7941726e5a3c8e124937e0156a96eb9bf99514c1dabb907eeab7353a3178c0f9d98942a4648f65267d6e9e914a022fcac2ddb8dc0d5be92ba1335f23733b2d8182a1f6374e371694ffb08d6f285f66f5d6069b46f3d16675ae5e0a5e38c02476142769e3eabb1669aeb39a4d371c0552e9376fed88a7b89b5c4dff1b9499e01e1c875e0405f57eb3dca3681d9427a4ce5c1b05246f11bc08c19826dcff9a54abff685c784f9afb955d1e7464e6a0ec9ec2eda96e86a321f548de066ff904a722ac51b01b0031d3ef558f85a324ee07031468d858c4f2a3589e7cab4427c14e019e51cca2615705e4c9bfae3e748c6c3131f73683f10c66378f3058b2c04f44e4d2cab6458941d8769970e6aaba40f2aeffe9de3d3edff890660e58b6058e415c168f92165572a8a776c57353a7f73ffb399bcf7659f2a84d58c21542af43aa98bbc943127ec37d7cc02c1adb4f2835fa55c63d9e93c750093dccc6f82cb99236b45a9b0f67a7c4efc03b1aee9f3e1acaf07cb85f5cb36c42cee4be2d5d676b7b383ec1cb5ca91b99376cf1e1f80d79023a5604258cae6d7eb122a783229e796fed47024f60a6b9c5f3b8a2719432817afd0e56959616458f779f9fc662c02882e65b90593c557bb0762f864bcffeb79b5912cb050cacad16e97558c13a44401416ba9fc91ff9419295044364dcbdedb9bf8d32032516dadc6ce18df3c672daa3fbd7dddeff04bf54b572c631e36c4ac64b05343b5e18f8bb0f766bfaaeb0cd18abd151957f200565ad4340b1b422fd85fd66acfe08411f2f504320d242d9ba0bfee9bb2ca5e3436eda7f2734c05e2329794da779c2e3320f848f75fa52a40a7e4894e4329dd65abd2b2143147ad530a5621e6368972580a0fea4758edc53bd83e89ceb882b96d153f2caed0499f6743b68500d7e396c8196fb3137f7dff1f737ba0fca0d7422ea49647da93f8a51bc65e0e60f6f65f867fed79f61300ecdd057ea4756f9a373c3cb0766bd92ffc77c540af450caa554412a25a42b4d99f62fa4f9fdb47a810f6ab749bf4d6928ad2bf3494d41a3795aa0d586fa606807fb4775d35d9fc159e7e6cb514a9555cf34bd3e4200aac6ccba1ec66fac6d72ee9bb1cc4889656ae2f01122eb8fb75bf797b2bc608117567fd8e592143da7fb828d7ec2573651bc5f86f6a5c3b61dc33089ca816ee45e2646781ccdd854cad899f405c2f9a91b1b954631e3213be7ba56f0c3e6e80768167083aa3de1ff0e027e8eba62780704f8cc0c24e7eb1f3dde6d424c467147195baeaf345df95959eb464a20e7063ff37eccdf3677199e768a6ee489561a3815a1f8034afcdb23f74b270b30d415393919d3fc4c74bea194157d7ee10d26328d4ad21ae5544f6d3bea79a4f69102b894c542d31d203bc0e6ff8c4499ba0ab38ac4af94a37c2d81b420d827c6fb82a65a186dffb1e130ae581afd25ff89455f73676380db11d506064459543badc3d00c3fc9b076bd385316d5454ff34b7dbde4bcd9c179fdcbd0b2bf5ad559a198d243ef730ce4a4751c43d99845ad0a0f5f23bb63dd242c5fdb7bc24d85adc0a4f232d7a35da9f49394dd4473587515f33f6311ae2bd26ae3be27ecabbaba56d5feb75ee9594fc5d94484ba675f26f02343a0e26c8a73828be51af11599f1c1edbdc317a3ce2bc54deddb6b6e33fa19c9ba3e55fbb52755e479d3e0dd48879fad1d602da7064c9f811bc124dd6d21c60dd2d63a0e952ff961e01e159beac4ae7cf31a357e89b793b60f642b5023e09bdabdaa7faae0bb1816ee0e16d3e682f3a3a8fddfc1e1c851e1167aa6f6693cff82ba9bddd2ba6fe54b7750db26284e789c4befc9c3c3f26a5e06ba9735e4cf842a7b90493edf5867d61004dcd6e03c4c36d84f6681472edbdb50f9d221c2f17516ae112702f6a1753cd2fde9062b9a51c10eeb34db458cb0365cd3e87e52e44a1572b397e85f4b5b80be4e1c6a9f9eb80d526fc9eec25cd4b7e8800b183607f59827c165c13e93a9902f0ff145c35fdb7ecb2a58dee180992ebe3280b3dbaf7c438f182bd307af3126a2a3b1bc8fa1095c4bb6a319993be560b695680e82eefbc9ed73ebf4d1722fda6797e4ccacd613405df8a17d7ba7077e89567dfc5bfc0ac4696cd196ca0be1db59e7cf1260f70bbe645644111206666b0200c2167a41f53843522b2e598003dcd08782b24961aff45229b412301f00d8f1e673b599a7a8fb0cd7ec84fe40277bf21f02a18063d7f0ea92fd309a19798c57f84acec90bfccf40c8a0b27e505e62e4acefe5ea42aa1bae53c4b6c78a754edbb23fbf1023ebf9ad50bf0d13ecd6eb0ea4c940cbccba78474c53b34592180f983850444d09146dc96877455490b3f5ab210eb5ffcbdab48619585c5d48a2bf9d830e9ed499a88f3fc4e53172e0401c70057658c654a8f6fdedbc70b36a0ab04902f024314bb3cdcee60e91ee52e8eef78f23c972ccc6f9090c2e8a95d02e3d2eeac4f59b337f6870d2007508e472801baa8391edf7a0ebf183d7f2c07dc57bd750f907d68cfe46b9f36a57072484bc039037b5aec3ef76303833db32625a6cf6afbaf30b7434251481b9c7e9ebd7aca21ae88ceef1375d0ee291846e18b92c2723a5c11c3e745c645cbae890dcde9225b68beb0155b667b67e57d00f2b0561f32f5b5ac78d6ac1e682b830b209461132ff82e11fb915e17920746c885a3763ed3441b16ebd03ac27b14c220518bf8582559ddeed3773976fd86d6e18ec0b81ccce26b0d6a37dd7674ffb768a7f9c5f08a44df30283a2900c79b8c99fc34ce409a9790ed3489503ff685544e4d74ea37e5a415f7352080838f528da7525a5cf76da761de3bc44c3e9445932418981ef36dbbae48171d8de682c1fcfe4c62137ce70bc736734f8b918dd64f3691aaecc6f5a4a31463c19bc8dcad689b50bc6eb1d28c813a195e492450d92486f3b10fbbeba7e470d20003bdc22030d5e94f7cc32e5c368f66af1c06fc9da6e6c877734c461f7c290fd168b8544b75d43c0f7e4a4b05fe88f92866a7c982e2c1d12020d203fa5d6ebb30b1063fcab0e8bf34fad9eb13b3895b2d195dff1062c880a7cc8d3a2ade44435bac9fda26d7c1dd6b230d8c3db135eeef5d1c44c1047b6f7daec3b6253dacd3020ffb52bd6008787c24c0e0bd934d6a62ae659321208771a0c6cdce7dbe8409e51ef0ddd68bbd9432e227604a5a8a1dc97124849dab301a8269b839325eb849152a09da624629c32f6596c54e3822727775a85fded7734925c4509b1d75ffde71bdda62172cc7a8383809f0b63c7338ef6b0cb544707762398f8ced488bf666c84c5c4aeae148c0f81a4f39efeb4c5e769957d3c82294195f65171b3acdd6028de35cc6694600f4fd86252dac12a97648b8fedbe5788ee251a8c352da024b1e07ad8c36c8b83a924dc9d6c92ed0f9cb599b9d700477897356dec58784d556c6bf4e505e4a7d10b829c7b357ef3a35022eb169dd1bcab48033a33b78bf2d8158ea69d28b11cbc5aec0aebcc5bee0045046bbfa841e293788ea4df5ca1b1908ceeb2b2953ac9b8f27c529e6a64321e5ed6c76c3e3762b9fb39210113688d3de026bd204c529fd0fc0865053a5acbfd626fd1f28790e5594e734f1761b19ca9dcd1a63000600690ddcf98dc51860a4389d13229b0306ab887b2fc1f91495adabb6028664d49f505c9f7d5ca3b6fb77296c8261c52d0c5121316a757a03f67ca478657e82e8e802cbcae83dd257ec6b55fb66af3010af55a2b26ce8770a419333503386dd5cc3ab831a7fa30daa83bcb741504e1d63c82eb8bc49427e58fd35a2f7cfbd0d5995434280cf6a3e32607672175334cf97281fa39b8ce0fe1d716c6eb64d57623e7260a471f4a18cfe5f9bf357165ea5b032ef2edb67940bb548a4edf5897e1dba3e3b3c66af003df49d8668f356fe999cf6fc59f336de18bdf683481103abd973472220f6b0c5e0b1550938923b3ed56b9470f0d020fd31dae50a3b39e43850d29970f8ddc32e4197e515289768609561547be33ae5726b60949a6f50b00685d21f095debbcbfd62e66fe3ac175baa0f8e6a1d2ddc9307750a864c321c746feecf268c4dd21754528b67e997c656165d95bb96409a78b4ea5570db1bd6b7af51faa1e2a294e4bdc2524e2cf4aece3b2abd1c3e41a7feba058025cfeae5a1cf53da8e6020417eddc8b104f9b4202088b2bff68c02e9bc1d818807d82aa0527f478929ddcdace8e61934c83e580bfe0ffa2bf2967240063c1a7494fd938a6d6ee6998e16046151877b3ffc088f475a6ffc8155e3db9150e524773ffd4ba262abb629086c0ad160d875c9b9e77ebb40b1f4118a87421e52ac12a332aa0676347a99df00603746ff80d1c5bc1348815f534679a000ba84447de1b911f4f13211ec0e821a15839b0e0c67919f5319da9549975542a6a47974634f341cf53913131d0640061e5ece9f794f492828e5280675a15d6b1225c362441d1ca4244b0722f3b41365ebe704580909f38f50457c62ec2ffd9e30f57f91f18600bc8f08673f30cc073ae1d802d1d7b406c9c1e6707c73ed5697dfb2a633e6a28303877994b34224649ff7e30324c9d7437a43bb17409b7baa31f21cfb3adcfdc6f466652590d9a23481e78591f76a4c5d890de2a087607ca444ad530e80e604372b768b52d88fbd28efe439efa4d3a6d76a75a3097796f484033eb0d9ad7ce2b28c7d647a6ae2ef65ac70c744a6f56be90ca4b1798a72bf1e3190f1067fa19044c78db1e45f063544f222486d0dd27eef73f51a892ccb92a177ce32f16161ac837d7afc731d08a2a62a8f1cdd7a2be7e940a76e6528581b02a7ab350db477ebd2b9ca7b8329a65144e0f1e7399b280c0895f05fac8e047814ddd78aea4f2b8a17a774eb15c650b979f56f49db4af280eca698f01e21c62b5e6863954effbda6e8408e3c3981e8a9f76b97d3157ccdb39368b8cacb94a64099463d8de4309c2a9820230fe59f9288c999cdb2066c8c2ced8a52baf44dfa54125ca595f3928641f9e04b982cb5bef1a83c21aced7fe44ed49e711c0fa8c33542e9a483","isRememberEnabled":true,"rememberDurationInDays":0,"staticryptSaltUniqueVariableName":"e58622878c5b4107a5c053c29b821537"};
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
