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

        
        const staticryptConfig = {"staticryptEncryptedMsgUniqueVariableName":"7db91719722da7889c5085817b274a97f481d0aaf7cf3a99c279644e812f31ec4a9d1e9a5bbec5133565af392951c42de69504af6d8f07aeb04f9a880d5ca902e4db847dc72c86aec9db2c6887d485e0d7d78f4591afaf19946a388407b3524319626f8f0f866342d39eb9faf5294e45896f8cdd61a6ba11631096448a8724c30b3e6b964837cc33071d84265ff32f3f233fbee4e73ac9048a2be0eaef79b64dbab29df76fb4abd0067d0967e5a96556ec9ab899882e6acf668d734a27c71eeaf24f57e21e2554b439e086639df6f884c7ba914030ab6ee248bbab2bf513ce5bcc5d6d37ba720bd520469263d40850c7f2f95aad03b19ec2818d407ef4f42e0f727f92cbccc13e638a894ad9a88c5d0f8539666b30f6a5e6ef38956fd41a49624b8aa0c742557d0a4fe99df83aba6f1c5d105d6e9f7b2ee1f0b2097aa23c6f4f7616acbf71f37abe08c4cb01838980706bd2a563af0f352e633a58511bcaebda0638f2bd72a5c87c3da0972f152cdd882c11cf911d6fc74ed28c2289874864810ae31f4bd3896ac04518cf82fbdc51da31fa59b2699418a495400de1ce2cb899b27c1d5141f1ceeb8cedb04633fcb1ae82452219b3e96b90c5cf31db31b9d8fb9c5de4e17a6e7feebac731cad599965b515219402de24a6472a951622e40a2fdd6706312d570efbb77291f464a3ff78e1ac546315099e5d8ce62b02e96b53d6b20103f5cce2781f94fb1ead5eb82da1290be1ad8d4f78924fe4777e23d8335070d5c83d26c5cf9f694a3e1165d193c983f507384ea7c4f6913c5651549eeeb465f19b8688f18200a9ce79b99092516ee9dcd1790b6c1161e13796c08357a4ffb4669df97543f2cd17bf86c406c25787adcb81eb01a2462ec8bb114446a47ca6a95a997560504079a4c14afb3ca3dd0ce8e6f8cebd5177de7dfc343b75ac94d3cb65293d5d0530420037917dc7154711de07a60b6ab5e9d2645e19044a0ccd590e6a8edfc64a645d468e58a400bd3168451439f311c8c5db75d69fff987fd329ab77cf5b8d1c36997d3afc67e520caf32acbdcdaeb782a95ef544fd15c22569536151173543eccbd7326927431dc606568af5d059f7be407feba96956cb17e3894106b70974e6c4df60b4be9ac701ce35ff738938c63da1a81e0c2bccbd45c29210a6e6c7be038157b47807c92512e0a242a28d9b18a8d90addc16ceca1b1edbe42d24e1d9ba4968443a5d7c144e44a999a696c1a43030ea332a8547b5249ee018d448662995a6f7cd61ebfbccde0ede698a80bf8a41193e0e9deb7637eb5f4fa9ff97b651875babf3168849799ab973e7e8eee025e0348cdcb855a8a76818e92de96e3c1902b70995035e1dab9a19ba24c9ea6b2d06f871151074a018cc263607eddb16950961321319ce8b9d8f5c1625348bee501e649825bbd58a1b03859309dfdabe79f7c0d4fc9f546c9c77957f57cddc3de40d7165175ea789e51197e900811fa47ee02f3563cdbf582b90254005fd32e6133835264cb3d8c8755f3ba33b4f46bfebb8e8d5d16d357c216d46ef8c2b2b018e412fb428cf7be06068b061270a482f42cbe38c5331664efc9981a5c077397b8ac299cdecde29c1481091169e7e585d80e0076bb4c90e04655ab1cb0ad930166cead3a1fd62c062846a7b6554f329024b57caa4641407e8a04648e8b7cbba943082edaab008d27e452124a26d14c742f272b9191bbcf82871b86857c86d3fac1f455273ddb7198f5f129ee31f1f7c5d77fce73f04615f5fa50917747be546fffd3eebc0db8afe034b513546cb52a81a48616c4615a2723124769f4bb6acb62b49484ba947b890cfbd26605e452c487801a3fc1687e61ce97b6cd43d00ab0d4cab397983966d9a7d356b90a93a876c6f4659ab29d9276512553c980373dc2dce55a18bfdf5287f1a96286aaf9549deb8141128d648a48af9feb9f7c30e194e33bf3417422079b7a2e176e14df7d243f884ec69c792ea0e9723cd59e114eb6752fd29d20838426088215f7275c899ab31078bfa7eda35ea68c0492ec2fc7631f6925bdc3b235af45b86656335ea23217dc5194150b0c7caf6961460ac715ffa7657f58ff5443c8112135f9a21682ba755d1617783ee3aadeccd1f9c74c9f0d574f918c46b9e32702d63d5f2700d780f049c6220b1f36846efc8d6ddf16a22ca87efc61e0856369a0c124fd33b2ec6eb3ce4ad3dfb900630a31ae638fd9540e3c7ff8b611d93dbcaf4cf80fc6ad00a9b202e161511b86cad54fa157220b43da9344efa65b501c61a46347d71ebdf40b1bc30c53b7988a7313f15c85b2d6668128ef38e7b570b6b0ca626d269ba3347e410b6ba3b2b58df423fa1ebc47cea4c54c473a2458f9d5c98cad156983777272d38c7cb687cb7e00ad88204e2661d5b42054aac79299e8db908b0b8726e2c00dbbdffbf075df329e435ed3008db11e111d56528272e0accc918c54eb75a6a23fdb8978c68a6843429b83244ed8d0ae9f606f3e60e0668eb49da64c15b91e00b8199b4ef53116264c7a06b4143aa9763918fe5ff6a14d3f578679cebf572dcc1b7bf975886ab0a5f77525937579821191ca418a2ded914e6237d5620759fa69ee8fd1911f5be131eedc8026ff09c5185c6f4f8720336351b4cfdf85736c0a1a9d52d8c25556afad41bac172008cd25acab21edebd7560a4d8b22de379ffa39cfc8ce9c412d013739456f106950fec3d82a226ce2c4150408260212f53b85e28ce74d22a100fed117d349b254e56c966194840bb0f30376fbca0d6aac88c97d7eca7278a3355a27c68358971229d611d9e37f0bb921f7a12dcca1c393abdfdeca124a0e903545d6a5ca51fc30d4889838db4ca2093a5aaf6fd0cc0b4ae3ba6fdf1563e913c04616884406db25e13221dd31a0696bdaef97014e06c1bef86a801091ad285e615cdfffe13a1ba3cf79b22423b7e0b837dfa39750e11e87e4069623b7f32664e75d47aa9979953ed9d9e2e53c0f34f48b5d20fe3b778385e878bcaad1365866c4f077f0c964a33b246c1740787d90683ad7aaa05d241646aa54b48c70980bc6e5a83c4e64a0ea6c758dfd70a026690786a5a03c4777625d66d94ea7db0858d916b174b2f2acdeadd3d93e742365e151448e14f98fddaa4e4e0a0aa0799576b78b3b9000d0a6921563cec18b577f74a97356025ff2f5e5810ff0b0b7720da919ce952b70a50ac22f1aa061b6e192e2a3f7802014ca2b81b45c12be2a74e43bdc8302e5c5e3ebce6238b09f7a31ef6807ccb0903990f96938a614b206d091bbcb12d9a75b07b5f189f337ecd706e7501fa0cc9c227b623a23e596551f8e4182d477e9fc8d69709540e14ef5d455653d2a026a065ac6c1d1fd7ab4aa29a611172d0ea242e84f85a9e8d4b0c93255e189fa240cef1540dff03b19ed132ee6f9a6a11622c32dfdbfc64dd3e31f60c6ad1918181ccd1138c08f8aded4be2de310cd053be218b627ce1f5fbd82cd51b21a54f9b65a0ebcd00952278b0cd544b0cc1dfd7f93ab6c700c86453c5d41354f408704a1595c84a9f48b52057b9fb9b3e00034ab19a5959f851d73aa8f2e1859545558dc747765cb1f545510ef98b9f1ab8c748cd9c654a7338587958635138dd7f880b1be459ef19d5ed4c0220cee51b1fd85c42a4ca87453c325463a631ae20028a719cbb6690bb01595ac35e31de82d74ebd1fa1c0251f18a1e06866f9f784a4becd0c4031da6bb57ca0e6a559e5aaa632a591c39739c14b8aa52c533b7969cd0f489ff49ae00f6830538545a9661264eff118df7af7482506f72b322753985c4c5a1afbd38733c3d320720318c26346d65139e97a22cc3ad3fc7118021851e1bb88518f8559c033a67e58ae6ecefab187490f767aba147208b8d6f9e88d9e585df8b959a29822c207c10930bca882687bfeb9116392e547dfc76826242bc522066d40f48de87634c6d14efc03154b492e5a3169b63112c3a8d6ea18aae3691ce29b5ee22493608994478aebc723a9b03f06c5a6b7d15207b0d347c299cf7ea9f9b3e6251af7a3789a94528339482494a5017cfcc0f9410f9da39f957c18afbf335362ad48259ad8d0c237c6015d3845ad530e8e9290000c615aadcb5460f9ac3f2f7697236b0c319dafcee7d0267db0a971fe87d61cb9d3ed54b2d32f964a70ad0d31aba282120c687fb7721ca12a825ff5145334cd86f3f6e8bb92d6bc48adc32f75bf738f9359c9d89a4f7dfcef0b7c3a948de9890f2992737f0a64d6ab1a988a66b3b5b4218aaa19ea2e2c3eb24dd61795e1d561035b52233306e2d3753dbc9c08514449b08b87e0b62dcf1ae8dc1f63f93cce7f96ff2d3229d69f1935ae4038b60c598b086e695388ed5b5723a16eb722d387dc2e352eec22c90e8ee15d06f4995406434b438703756b7778c9d34e34dc5b7cabd6070df79be759c7b66f6fc8dcc19b9a6ee6b9379ef380d1d44776c537bb01d17650dded2dfb0def8154566bc390f14944503427f015e87836a0b6c9f56443eb530f923da85bec4331fc9da6568330af56e987608b1170c97c952bfb2a0a45f133b85e5f8b0daa6b0102b10e7629c1f628a699e18d426f95ba21c48832a9f379b19c09a2184b2577b738d8c539cd7183241723ada633ce5649c77107a39ad2e855e555ef91a386d51686d688f01c6176aa141b90ff610c58fd8d9a7ff8f0d5efc4069898f538cad26838cf508dab242d3b958cdea24dcbb11742d8d367d419fb57f2c76a342c47a342ce6a5d60575b8b53a9de847fbfacc4acaef6fcb0c5b075202152ac2b4cd15167a9cd8e73dc86b6393d6301aea825549e4798aceaafabd293a914d282505571cbec3f1b01510de54004ec4de0322588434e12a740c35d417e715ca4b461d3d05649a3761ff5f7989365b328a062545a67263aa6be03211d775be6ed5789050f9cc582193bea38319b5b8a4501c8ed88dbd38057fd8dbeeebae2ecd68a4e94294575e82a0e0ed4756409339f01ac578bc76ff4997da6012d08e91e0fc1e0d558d06274e231c154c5b441087b1584f49e98f4b0af6de64ebca881cfd200b681cbab1d128a15d2a4e9adedea2b7444ec4f8afa0ab2685be5fbcd652342ee1f0ada9efc206352e561768ddb032d8ae98c4d4de2b70573736a4be1373832c3f4bd4a4d728bbabab8f35b04a2a24d0c1a28c99e08aa247504abec8fe9fab6026c382deac43e616963fa6401d3eb5c0be385a1781449894d6c41cda596b8090f68a342cdf63d76c6dea4d56871eef89eb71b158a80c98fca7d72a5e5ba245480be5e3426a3d71aa2a685f619c85256339f9246ea82d7421e71132042b8cf5db3a1a520cc98ea55d8319c9f3ce1c24499afc25aa009ff7b341847677c26dabdc6128261e00c12501d7162d2218dec0f40b2384503ede137f2b869ad39fc8b2ffff32e74f0c42e4cd5cc63a66fddc84d0b1397b78097efa55e80bb49c06882d59d383116017f9997367604077b4190f8f262d5e48c886c5cb951e16d9e0fcd799cdb35f5812d2aca05461e9974481089a631e771e38f0e0f31616c6a7ce1cba20ede9e0a9556c33e80d33fefebb222f18ae846f90f426d3b9052136288ac1526aee5af85fa2619c5385583bd22650a4fef64a872f5eeabb8575dc71916377ba29a372ab19170998775f5efb60f5f1805ed9fc1e0abd727dcc3f289af2e44a2542131f7e56c16a8cdbeadc972112c8735b023c99ceb22799136fdca41a16eef154e35c01a121fe471b601a428ff0a6e113dce9eab333feef7dda6637861fcdbf398a829375ae95f7a8a45d74899058e93d53b6973e830aee1c3a3ca44b630e6ba6105fad11e9dbffc399dfbf7bcce82bdd0f4f389196dc77847681775a4f48e26de3428f056b1d100780d6e7d2c1e791ad42f659fcbe1d0355f8c4aebeee4fad78795dea44a87fe2f69a5cd4792ff61628c5fc6b79ce0915797a3709a565a0578cb46aa30db4954e7f874281ec02cc0ccaa5db54dc0df3a3fc7a0e741bf6464d701cbdf4de8869d50b9de7ab92519502de96e36b02f7afb352ee7ad55cd45704f99dac131b0c2bbff66ac61152e63a110724485a84961ef95762d5bc3e9ef2b08c58cf941e998500e0c6f26daff865c2f5ab33c53ad2a85628a82f313667e4a9d2def86159ac5bfd0578cb5434888207049ed2427b358d6213f8237e4256ea61c12ff64d3e1c303313501fcd364c7ffd89849c2ac448ea4fa9cc2911d8513c4749150a0d3b3fe6a83dd83e2b91fc4e568bdbb67c5316c1ccbbb522d7fd592f1d3c2f808f77289d404facd745413f0ea918545de51c7133e2be9622219ec42226fa0daa1a0073c01d52a367e86af8b8f60b82c4ca1e3ea4dc3e64e4ece30860a0bdf4afe1430c813e811a4c33f4f6254cdc224540f979f9b8f760a3e4592c5ffc903b3a2654eefa97c99adb0cfa96001c8cd99f34448f1310ff275a4343460d9cd5d050f83d63f5887c3fd30d1c780dcd941da4cbeea26e9d6b311fd418c862f8ce0ea4c3faf9a325df29597f2a78a64587f929c8c2bc9436967b27469794bcdb952cd1a81d484679875c3ac9d18335cfac25ba632c35cfdd1e5acd0bfe64e287be91c4b7719273ec4a4c1cdb5bf58ed3bae107abb121020ca4bce5ed5685f6282711f81038d56294e82af8b1a78600d109da20bf199b5c192f27dd5b7d2996c196c6726937f41a5f481af2622e41b9369c3b599c06ddc5ea99269f1f0730d0dbcb5c679dba08829a7d5ddff6c2c6a0bbbd4105dd8f6bb222fabb55af705264e88793b106bd2a85944a4b24126146a0f5cfc01f2fb520c47ebfca41ce6556139a91943c9399f25a58d56bc4f307fc5e0ab963b83cfd93975a3342d502e6ce28e9b1d04ed4d40519b05a61c84bc2bc9f9885e9472887c214fae4de40e27ca0be54c41469a30e306a861d206a650e9c2dd8aa30e96199763bb5b2e6d7d85c902994981b7a79a353e6999572c3be79385030ce8d6f15639bdbb9636e9cfbbe8c3e19ae40ee73b0e4384b57c77403b9edd9df11ae0b92a4962fdf3f2437bedb21a3e7454f5a44f800a96e15038c68c5ea390e3c0d79f26878ec04a8cec37df7f66e1b07ebd598380a100ccfd8baee384c7dc32372de3d114705ee5f75ebf04e994c7d5481881367d0de0e8f0a90e60ed7b9fd9760892cd2d3676fee94c4b60f5730bd8f7d910fd8879bd52db315e16b69464c9b42dd73b7cf2c32e6cefe557722ec7ae51ff8e8ebb2aad3955c6d963e8fb3448f214aec3733d749eeaff8abb5f63b0852e194bdf7070fa93548098a91b9afd65003e2f131e09c76d8f947e46273c92094b2e758d22c2a9e85b5c634241edcccd56fae49001cfb2b87b7071caa02edca8e589b0c768fa10d5f8f7d6181c32ba45a7347d43ff514a92c663580306cab19991e4e0fe9bf8876048ad7ecf8829cb51eab1d39020296b5a59d5f901c771799a51a1c4415ca27361f65a9cf82ce449456cd72daa31eaa089dcc2dfc3d3a0912834750b416d8522c66b86e91f420c6bc51df2bb2775caeff3f49ccd3b0ca5881e8de245b20fb3b31b120eb2b49a03632795ba180d18f25165a81607f638a369c63ae9236468431470fee3fa800b33d52679d0c7dc7605cddb8efee37872e977ad3723e6691940d31c46737b6705b0c28ad4a445c4221eef4709d687698392d8bc44994dc8f49efabf592e06a70a735cfbef9252350b61b7db53a6758de528149e509ea50e0c2bf777ad726619c966d341e762d7fe5ffda157fff4644f831adc12927b17ff0fde8d8bcf6e761bdea1ec57f9d1dd966363c8f17ca2be238e9f844bb54da9a75a66c3090b0a94a963491763f28e16534a462c5f998f092f9971618b8a80b6b1a473811156cfbcc233778659cf9fe9b6b91153e3032367e26034f5547071dbd6cec5da08975443291dd8e5b3ee6cee127374f79d51a07cc5cf278171b56addde4f13007f6b8693521c905de525c70cd26597d5070e34b59dcf6f76d86e42033dced0e0a1e3b8c83f746babd1f695fbb5fc7c214577bbc31f0b119c506134aa52bb0109dd51b6fbc842590b6df2e18243ded0bf77f1d4eedcf5455bea88870e8a8b0ee985afdb3f0d89b7d952dfb81e2b4592f3bc171023cdcacc5bd314ecf4f6853946bbcbc497b5f2a119cca8e1933896aa7d4c87f406a9ecc909528d8bee7988fedc521762bc679d2969c5f578c592a79d136ce9c13a2648a04867e188728797809152f8ecafba9e32969654bd1b91bef770641e3b4c991fceab9add87972f67effd43fe24008e8527273f93a0f53dcf4f6a03d4aa7d83f6cabcf0bdca08da68c7e9bf80e6107d21a6073b6e931983fb4fe8de24182bf81df397396d91ae7cf70aab32b674b62e731a311b1d78c61116a30f6e312ecfbf9ed84e2ffa55e9b00410528ab82ee6229a0043bfaa91c26a6e058e6247f2f2ca223c7c1964a996e64d39dade9a8432f743d616df0b6b1fffbe9d7fd62c69d93ee8171f9e8f78d1c94c295aac54ded69f39655c15ac7896b281f254d40a7bd62e8e7c55a06a746c2f834d33a51a537773f076c0126f8e8e3470955bb1d44be686fb7f15f1e8db7d3000755a34e932114b314f09a04011057c5041c7a7242084a8b70bdffc2107c31097a90e9c1ad44b8307a100af6b68ce981f97de723f65ecd7b8c7ed380b839528edf9ffb6cf3ab137b96dc54b34fade2b28ff23aff16ca2775512e3ac2282d134a170020b679a6a12b15c4be35cd4e44ba140998f796a204e8a8365cbff0bad0ff03033220db7daceef7a35f86c2d84fb57e8fdf5394665d463d9445a7c9a287dcb235e56834fae2e1acf1050e35014066ecfc0969c6879fc7d7937f791b13d962869f8c5a7346f9ae719e51a8b9b9d9e33f46edd87277672230951758b52ee0d6a43be61596afcee2ecef1831f1e44290c5c05874b3f8b107dc4530be3ef245c68ee5fddbc5a61cd2297ec9331fa6677feddd6fd054fd400dcd74b607b945a9a176ea9b063a80e5bb86298cfaf901acc6cbf2b198f63d114d3f6d6fe77dedec369703ef48220983db56f2e2281135689bbb8d758287508b1a48387f15d8e01294e5e8edbb662bbe6da1c93258f435c31099c273f666e22c8ebe65b87b61da4d3ad1c4938b85e1d4ff7bfafba2739ffd5e759c7ad805af125e35f0592f634dce289ecabc643c215232021bf21e7cbd0d35256d9a2825fc7cfeab348a18aa6a5bb36e2a87cd710bdb5b0822d964f3ea4cffeb596acbf3c40b16a0f284ceb60bddfb65aebc2e0a588939c784d9cde009a0ca298acd6c4e6f7b3a6a46a604afccd298797eabe904bd105c5ddb1a886b1461e16e53f92c7f8e40bcd4d473063df40e2ee8bc55686ea723676de1a4c24e839c2f0a1f9d4ebcc1f29e9b366db4f7b8d0b4e13365fb014cf72a1bd26da940915373d8566fe6bc65650912eb50ddb1e71250f4b94e6e32c9d8e8c5324fb6e7f7589d5a910e7691c39b7babb779f87d33af763c13208101e2f4d1855af8e27ee528fdc5001f9439e38e8e2296b0257acba3fe05e751eed5ebd370c7da125ec49dbdd8d671527c5ac1b17d19955ccc57b238e1d85b79fd197f8947aef3e7357ba85b790c5b905136f022f2f511a9c9b42dc35eb18ee77787c96bbbf5f2e6b030bf95c52f732f3f6c799f4bfbf77c3908930e5b693a831cbe77445cde9bcd89321ca9c150bf26781cad1029d3598dcb7eb70c9825ba2489df18844fcd1f656ef64e7fcac41a1c9c64bf2c47bf04e9f401254f640818d46fcb9e0709b8732d13929f7a1dad3b92cb3e622e53058d945e8483325c66f6ebb19e0df41ee3146ef5c9a0b3b8f7c131b33b95c7c53d22d7d13a9308c75dbac76edb26f9b4160ef806fd42619558631abf2092dfb9862d1b5959798f88d972525b261a1757663994d2a007f963d9782129669e116a3ead6ed76c9e0be10e276799664ab0a5c21dd6fd0cbdb196846c969ef5bf0e252eea24d67f22c286acc0128a40735c9906272300d16f52f9545a3897bfff1fb2d4230c12a2f8c5f08f7fc4f37f5872ab95429a4fd27aa1f694979ec2acd20335e3b5bb872872ee20cd749e2cdd6cb6ee9a1752c6b906d356b3fc7a6ab23184b2e851fd549f0a5bc584e123e6e7c571ac82ec7d33d26beb183c2078e9e1d60ae6621bd564a4f82b6c80948c605175eb7be7d9e29cb59233728d4f340d1e34c3fa6f66855ab7a99b52904471b547b6e7c37c298425ea7fc0c1898f71f1ba816d4446874d7cc9bd9fca5ce0356bf8744d8bd28ad77a0f6a18a9bb73753b965955ba2d02342a58e3d670c1733ca1d643d3d5fb0182ae2cb905beaad1e94d745cd0ea12d637fd140a0b29459bf88d84f9b5b201dc5fa3da65a2d6265cb7afdfe6ffa48232b3becaf9f194a8bb48b2ec568c027a3803e1f27c8bbf410e5f548e67694a1a3ab4b44056e7ef4b23f297f7444457d2b1d3750ea6cddb0263cd1a2032f479fa9be6a75cdfa191c2750987d0734f0b9629c0f21a75fd0a0151bea3ed3986ac2c1f363e27e4d2f1292eda6756a5d7401962002217c4c8638a109eaf2b1bc1dcff7e3616291dbe9aaee2504f817815e55c6f717dae757d44d8531b434ed1273f422a338fa4392174107e55374b22d6332cbb8871688d1e768b341212cf2c3344c4800017303f9758fa7c5c17b55db7822913527eaf16e4751e7f3a0b02efbf11b19a67e27349208216f626bb9a4185981c1e6622c5b15ce69f340579487aef1ffd79bbec1d42b6d30442797e94d572c48f5d3f31b390bba33d676a2ed4eb3f43fa30432948714d3a4a54075060020b548df0425bf2b29b61b139ba6e6997c27abe718b9352853f87d0e53a67d778be7ce1b7e4ff9f835a35a5c193644ceedba074a91fa3e82210dc1fa6b18f4b30fcd59d3863c04fe98bf5b428cf43d8c0c233b95a67caa431bfa4a90ad920d55c6b77731d909badd23a866e30ef24c26b258b6755e133ef7c11cab9bc552731155f4c0b88ae8812ad031bb1fda9b9c6d5535a4b38a6aec51616ff72f76cd7284fbd249b10f60acdaab8f1ab4e16f70ee63e60d6a875a37307e5005ec4ad7c9b03693ce2a2466e782aa9bd572470012d8acfa6afbaa810a0605fc1b4eee851e852c819a1e008dd497d7473612d6d1068a233959a450eaa187405052e64885de60c3d1bb5920a7c9931356da021b7dc2b814889b3575f2471594c58213b0b4333eee925cc12b9d482a265110f5128c10dfd81b520a8888dec6333caf968870bf8fd2584169389f51d107744f9a52453f54fb61897975678b58d24a2e95c8d21d2538ce8c36d59343bb207cd5103716153ebcb7ae4c2343eefe67076a7ac070bb47ddf48efd026fe7b84fd7a2a444a932d236b78ee4980a8389a303aacb59a5578abd1d028e444ba40008bbbd4b5c4501bc057d9a965fdd7db295b8ca5bb7dc6506a250524c67f345a2625eb7cbab4900afb5f3f3d2d41cdc309ebb0322815a77711a55f81c9a561254896d3f2acaf24ad83488797d2d23525fc6ab72dc9d02d4cb61197be4f45409610e907cda33999640314a1fc54185d5a33be4fe2d619a7e6f5ef062a1786201e703805b3e9067a318ec37cd4eda6e6d2a240c69be0e97655715f2ae2ced847d35d629123bf1b92347fa601b245ab7d8dacbd2d6378cb63d846bfe344e60ec88cb19085dc525d3dd808bc0eddb7255129ed7603a0f565dbe2d9409352f8667024ef0f9593f16e98577831747dd79340aef52173276e8ce55826150106f11bc73fe7b24be561bc905de5f38c19985d71f4b54cd8dd91b2891f4ea89da1440cd59ce7a2ed13626168d0cd5fee1a4e32e947bcc3ce1fb76a6d25d47f53fc8cdc0d8cd7e9188204f7c994515130d7b0404de163ebad66f98630393bf8e5adef0d00f6072ff8e29560ff56f14a11195c4542f0d5a05dd35bafbd2d7c38206dcdf7f7c9e6469ba634030287dd6628eb4305241756d95b9c3be1a39a4a5d317f6bfa52dc89afd40e2975e91b9c5cb9a20c74d077010370d6cfcca5fe0e6bf6a71e5cd7e588af6e99a0d6ef9d7c0db547080d218e65aad2b8ae09798b012d65eaf4230b3b7a9b48b3ab5b268ff8a0cc922367423dc062323e032e9d71fa21d30b098ceb425fa067058edc6e0dacaca4dcc473af9a6435363bcd0bdbd4c63403b180b3129e57d31d8fb357283ca2a85268dfa6a679f1f3f5921cafd2bab20f5fa1e48ec267d08c6c2598b4df1c05729a6d3f7a39a208797a09157f8a888ed8b6fc08f72e196b0231fae99b41fde506d234b7ec0347f694e187d084fe03be2d47454dbc37a3b0de4d59b541927ff43141bdd1975b84c3cc7242ee27d651ee21cb060189d4b4196e744e964156c2d041dde8ec8e1033eca257033327eb2187fc059433c12a547d9e542c35e404d31d0d13ae2684a695261c87695b2b6d2341ecc77baf67566854cd1b59d65305e0b9bd14f3aecc2600ef94f3439a9833a76f3afbeb7b45127e6ea82c86a4d6f591120db87151d30dece78ea7257bb89e38397179de8065700277ba4b6fbbb887e643d1d7b1845a78705a87cb5eca723e9f065ef5320286770e4ff7ef5ff4c3145e2badcf2dce2f6939dd93371a09aafe12a92a63307f037ffd34cc237ab04560194fb84d8041bdee9191b0b28d50244d90f01276dd4373086531df722f96e6fe49a78b4ca8be20d25e958d748f05b71a6f268ca25076efc461e2a17386654a8692535b292e53f12b73ad9493c99fd1a38863d6f546cf48bd037889d725f6423c91d8b619ff663e37e998d4e93db73fb504a5509a8522554134f806103948320f74fcd5d42ad4c5fcea7c211a7ae4eb8eae70b1c4629468173cb2c21c4c3867d9fa05a9cd62e497cb42effd447608dc36bf9118403dcafdd165f4fb2bfb1f744a43b1a9ae0b1d59ca24898a73ddafb9f5c4319bf5eb48c377bc6bb008d97bd87e760c894227dce858c12e041706276997db3933b28c7986b43933feed4c2e059edb23c89ddfa3a2e5609ee9c0b4140f6b2c29e466ebcdca2615fc9fb40edf323e91f10e858fc61117e5a7fb75348868696499ef759c34afed214dc28616ecf36570662464bfe82ffba22b51b4425111262fc938100b9328531a85bff67c21354a7ce7ef88b3137a432299cd173935a043dc131136894d05e9765a114c78ce3a4bb5bf399de50de2d4414a26814be7132162484346801c93a7a1771b86bb4889994c63994d044dd467b19b9113fca168c88a7628b41cbc0d41431f2ef962b2c21ba65d110b09f27628fbdd054e094a38ab35e71714d27175d7cdb026c1f8e7aec663066d818afc90aae69edb8dd3f294a3cbefb16f89523454b7dc558a48e267b8e9c4fbbec6fe6e8ffec5ae81f6078637f2793ed94e884460a1aa19760d9e0c0896c428fc57d61f6cc0b23ab2687213560f60d4e48e279ab79db4b1abb1aa4c12e216d0a110a197ebc5df49d8bc474c194bddbd2690f357f9975dd3a93e32ee27cc3566e730914979d80e542ffce64fac1a2911fbffd60f56b0398fe575c4b09bab4ae545c4fcf5a7ee9b4fe91e9013470172eda2b1b16f794b7b3505f27e28e2edfbdc00a72ed47aa2260df378f2dec574f3063e81a4bfbc8ab4425d2106718ec2b6529d4d1d733d899396351d91a052ab6ba4604498e71ca7490d39061a39690fd38e07566162cc470a35b63aa1c79dbc7445ee43cedaa58547b48c50658597df1d20476b683e756eba1cb7afe5ab0975fe0c403bef9607179110bf50ace7a59efa6a1be56cba25c5d9479e67ab5db7da887dfe493f4035a9825c433a76f092cbbf2c00c0cb507d40a8388d1de9b7c06a597a239ac011634ee2cedc1ecef78f33c047f4f11e2fbed441760c9eec4aafa5e206c0be50f0b937b384a78abaf0f2bfab551d51ee583629d063e6fd3bef78a084fc5f61ac702e31c09eac3ec88fd2f5f67234f6d1c14ed72d5d32483545ce289b9f0e43b08e0ccd418e0799cc58cae641ca22b6219711704e7e9278a46c2a3a3fcbc69d6a0c05db11c83a414c0c7282e17b2687dc9c70a0316233f416f1db75edd07896bd27190959a95a78df98d3a2e4a8ffe5dbed0ca2e46bba4d4cf6a75ee737d23976a3a4e477afde78dbaae7b4a03544da24de7fcd6910ced336f223bcbc92b3a5f67328358383456a0c2e3ae8f508ba8eb27dc5d86c008443e45dc6efc4a52e3305067f99ab95bb470fb6ce330d6dc278d45cc4fc83ec0ae8d59701548bbe4518b63b2cb806a4b04ca47cea6b504f23dc79e6bb46fb267013b124910fd5ecfebef804dab5a3ee9c3e7e64c61e188ca189227ed06d4fe2b37f1ff7aa758bf7ea8e55d16e532d3db48c05900ce16a6351fe5e54c529e1d4f6193551d1edc749a794bee0f8aac044d9890003c898c6c218fd82cfd856131b319b54ad19478cbc0fe0085a1461f879f31b91e7f0b66e3a5b3840497b8c30abccb91749e0474f087e7fcbf6882a32bc8de0049dcba7e2f0ca599c7d4bacd76243e9d08e29a236877aaff17e9647f4b84a45afb57bab382be3c6eec2a066ba3301bbd005183dc7cab2316394a044001ad13a0c5415fd020a33dc2d0be619a8b95aa09e36238c6bcbc096c101a6e74daf962a991ecd4084a404ccad424e7cc2465df53ae96afa6dbdc711fa3ee0a05e168d531f141abd458d2a0e8f8f4eaad5c0c77ff4b1b4f00189697b51e155b035bc261510d30607a9993efae4834e66df988a144b4357ae31962adf179dd6c4f293a2b665f0b65b58fb604fa45ce619ae0cec4d57533d711858084aca2b78eae2cc9a4abc151660486dc39fe9cbeca87a62e3e4870cd13addd269a0f902b0803d3ea78bb4db92b91804c37b0c8413c83c848171a978631d0299d723a2efb0f51b9ca26960e61f4c202e9f9d4c2690c13951d9432b94d611ebecbe0009c2775516b30b1c9276e1522ccd12b7b4c559732d15d269f7769c814ec835ae16525115add8a5a6117638b86646b8ebcc501766c892999775814746009681d327524e344b25f57697010efc37034e5671fb1e22dcecba8d5859e48cafd801976692b72ad70deb42ef6ab0251ac98284ffc5e94baab79fe2930e2cb0ae291585e3cc1eac13100d80a4bd43ef2a9da3d421212d6e7bb20810acef53067d3c36b9e31d20c452747eb5bbb22339eb3188f0954f0b8685fe7ea5f2d3069136c4ec540a578f23061d0eef886a048b985a5e0319609da4555fe85c23ddf1dd918ca6d9bbcf369df10687eb20fb5f66ae128b061342a7654be81414a42cbfa8cff535d626378d119963d46433c1ad3b1a0b9254bb63bbad67a9ed94fc716fd64e1fe6e57c89ca620356aecdbad8023bc90fb6eb5584b949d7663f1ebdd5d53473b7f562bda1b3098a132043a4ea094681af456a98946a2f87fdaa20740ab22bd478ce1f8d633a16a63cfed1677633235382c7fd88f669182874e4632b448959929fe1389b6c87092314a4ab004b74a92d68e2bc97c01fbc1c6b8bbf9450a6a054157a8564c337949634d98394ba3d71697ad185538da9508f606979a2e85eb101fc4a4456e5892d968d0d4999cb54afba6f994d42e1afe203198598985af66075da3677c3bd06dffb48d87c9c19372f23987e345e08a356802ce3d237c340e354ea6b39210f74eb4ee98f69578fdb2c926d9dc7d14106067e324d18f73da5558837ddd7500c80f2539ed26a48e306fcf0466c9d35af5f05b6eaa39efb53a1836635e17fe96354e4cd16acbdb91c1ba91669df0f82e2eb7a0ba7e1f308e4031095c5c0aa88dcae3d71116e25e3aaa6c214c47e9a98ecee32c8ac9973c9e1c4bbcab552f1140965f88f21a53bb79f63c1901d105558f4d8f152c7974f2c9e68fa378ad4a01673774241a37a649c43e626878d443604e47fecd57edb78bd42c0c55cb62f6d2e81fa407b1784cfcf07b4b38f3456c1e20f8526836d055ebbce1facb30bde366d8c8d57355d0cfa112ea17579e875768d4ae311055e3a4edd27be1d5b221b800abdaecb1e4e6d9fc7e8613185ad10ba27c85f1536688c7cad89e7c9ef1ac1e5b922a4f77d9fbe4a16436433ee85e26f6c5769dd8542cd199a687499fe79828aa2a7130d9ace52ba393b9c7f2f9f7f05d114a9b9510fd50723ddfd4182dfea9448d7b9f7b5ecd0b7417efc6d2e270b3a98ab10cf0b3567ae2a98256fc7f827da2f101d77bf3fd91a4e65e446b3546197915d73ee93d3ad3f54c7872426381a333670145b174af29267b59bea04d79b1371877f5c26f000604c3530b1ff6d03da67c565c7a52e980a0fea85c06cb35a9484f4d984ca3984c781844fda66124da5142773d0dbb85d3cd4c1b7b7e0edd8cc23d9cd20ee29893ffd71a3c05caa2458c6086fc88c38c390b42443173a615fd60700d1e38a7d83ee0ea0756ce222bdaa2131fb5c84acb2cae2ec4133fe49ce0ec39a4fa6ee9b3aec324182c1c4174afe1f8b34f6b8513429256ada624ea6391c869c0bfa251daeb60857f59e29e24463f9ad906ad2eb58f4e3fee361f717f39bc0bd5fb3c26642ba776f4a70c603a6de00895b8f505f2edcc2e3f90ed0622bd7f93df70fe003ec069c029dc57482baeb332de56a7b2e3ab9b01493d9a955a027f9515a58ad161a8cde3c740d53ff58bef5aa35f5199b3fae114a7ea01ca01df32127a598ed4cad9d4775472a9e361fc27eca311ccfe15bfc3d50e86f6bad11d8bd2b56f6b89484b70c01012f707d4369593a3ed5bbe8141648e35829f1bbad4f8ab689bbfafea5802ec3973b8791fad3c016b989481cbd04944f6a72bcb78bc7ec45eb3905ff66ffe164c4e176b890d137ab1c43e593df4f479d9dd3ebcc163c854b142da9a77c53a22db8bd7868356313d8b7aa9b5d92bf6027cdffd324ec0c1eb55104ac8eddd648d8027cd258017eea2a4c16663931f7c7ff40d7fe5654a20999fe746ce013808ffe3cf4d9009318fb6da36a17a3aca95632919c01aaa2e865d1fe6ffa7926b15fe7f776310a5965259f47ce09bcbc7b44b7d1e483d555460576e1f85809bdb342f3a08dc97c9f038d2f8eec47563c41ae0b59d3a971947060e25ba3e0e3a5b6542186ceedb6a527e378498d8966d42a305fefbc42c1a55cd2c2a45ad11886f8a3a861c7ad1fef42395b2f278195bd41c81224da4dfb6bd16a4df342d397fab5612adec1d7eccd0a0130802f1aeea9fa9c5ebc6c78ee197c78982ddbf0d4fa01d76aa80833f14396a5e980fb8604719a1d3c3dd9b583ef3fd1ef43b900d246a0aa4b2b8734ed58f49a8c60c0b326b28b59f106401e97bc35c1bb5dc4b30e1f7866817b80e9ed386c50036790852d2af5e6bd332c7a13d09e3611f9127c136bc6e52c75b105c1f3ca2e4d71b0367cb5e7342dd82b2c8b269cfe416170b185d92fdf2d45e3e61a815bab6f0cacc8f98b55c465cbe94af7372d884e6221a9972f3c92bf8a34fd368fa50dc2486ce158cc00b6f3fe70c9b5b6df8a1f9be4da10f962b41543657439d16444d958f5de5a2045f39916ff2fcda2bdd23cb2f7027d8418bfb3263790233091b5f98c81fd6749eb68036dfdee4b74160af2d4bf7728ff3526c13fadf60f73a47f36bf5bd58f58b42e667a3981e50cc90333aa395f717925cbe30de2cf7379b90a1f86b0782caf8ea025bc779c2d7ea0c6d82b0e8779f28a90e8fc1253c6a9d1c1064b9a8ac9881baae9da5f4630e83e75a9de3524e3544268c79692c1f3a9d78f6beade181b99d42d71dc9dfcdbfe2bf7ee423000a889dde814957b90a338b9a019f7f6595642157f6643b82dce2c7d4066e8065ecbfbfdcaaa4a10b7d4df7da705191194183114bca8d3f8269426b18513fc622034e665de7f3aaf100d1752319b796659dda075e98641c3c0f9a4ed6efcc46e834d1ab375d3e973fd260dff75ea35ba5d569c1f6c024142a3cb28d35d60a8885ec6f474df6ef19a49ab9aae62033d6d67332910600c0553e265289d6e781ad2d978f60e2b665836a8ca769379880214feb7e97638dc667ce1ae07489ed785d850bc1993a5a1168e321d86abdcc80f1a3b0d1bf1c8a62d6c8f282d68df7fcc1f31229739840a5a002aa38d1104e44db7ef79fafe21cc99784de2c01fddba10f8423d2dc6561417ea4599a3eb2147a8cc0efe82886d7ca0cd7f6b7f99e8fe7617be4013e194ce5817b9fc49f3250196440bb94194bc324894a99fe6879bef58a8168fdf81ceee2b6247145dda3d3eca06581a6e9c11891d8f49e8d71b7a585b99c79ada01d96cd6bd813661301288dcbef1f14b235f54749aeeb8192fb49d3d61f21f7e6e4eea3a25a9285af91947557f19e13d2b0d4cf806d5e628561822a5c99310dec4a8db759214e39b5fc52658833ce0fef1466fa8a871c6d6fe4776ce76c31657657d71b5ffeba6bf5958b395470d0bcafc86efe1c8b3db850ba848af9ab243dcb52facecef4df63ad3cfa723fa2d0ea7c35d7a49993776b1053147299c7b694317c029704851767dd6cd2879c72216585c131c5545653e446421e0d4be8db6852ae10366dc3218f845ce84de52fbae3b1e96d40670d09bfd3ea1e8c491bd902bc366fe3502efa9c7518d45cc497d84c9b5938d0869c37e731df3f3db6ee081e5ddb075fc6fcc9a7c939b3a9ba86e0746ed87008c3715817e59059960e35337469fa1e317eebcb6516f9cbc674c6f26e6a2a90c7987513d81709a3c16f9c2fb9bd6b9ac464c14f341e52920d8daebc82836080cc49a1cea88d13af79505b461381183a58fdcb5eaeddb665c2e2f337300a5f0d1241f3bdde58cdcd3716d4fb2a629351ddcab54b3d4ac3c17ac48e5be47c4225d572eea8b2a76a3625ba5fe0f8ca17e99a7137f546ac17dfa939103812d2bc0255a5262095df58aa178c31001abdeb2bb20df1a21edfd5dd59c58a0e94736dbce7da031b75b3146c5c5b115eae6972e67ed2ea83738cff0dcb16fd3c2bf938cfaf2e75fe1cf02af5c43ddf34f538cc9ea319f12ecde385bf0f8ec28fcef0426585a104d0d94e3c816e15c0457d6d03e8aee565f8e597224ebf149ca50967e5fd4447bafa1849e1904f8247bcd8c71946adcdba8fa01ee62d7f3d2e25b84898e973857b368701d3b79ac333f5e4e82b3e07d1767bfd504e67532701106985cc5d1de99c4a6243674af4ee2394a20ff1e8134f1fa89f80a6a99c7e24359464d065527a3fd7ae20f71791df8ae83274847d146cede1925c77fd21dc346053a77d0cde9cd47b41ef85cf77bbb3f230b1cf66f3753d9369a64c4641824eab655381c1c3f05e63bd9cdcb8e051be992533bc438d227c1e40cd9229b63dd64aef97d2a49a4aff05ef9a884d637992af9ba1a4c1198fdb2ec4fee9c586c8848bcc85b20c4ec8e0a9ea923c5548127a4bb91eeb7e17a920807d1f2a6f792cfea887d409cf90ee4eef3e70e086d0d7dd201b033100ce89044f9e4b29d35dbae3bbf5eb3ac79d30b8ad6951fee16e97a995f48a0f93f85f7a30bef24cee940b41f9be846e1761ce1ae4de0fdcc96adcdadf3c69cd2b4280728c73126fcebba53649bd5ee6bb960c060f48871ff226d756abb7a6df5605f3a044fb5bcdae454f6fba577da5d1a882baee0bf55615272e4b7922230a44df211443016c4c38b1c44c2f2dad2e27b14888afc60695db58b1f7c20fc2435961d17dd0e3ff30e849b3ce9f31ccb33506462695463ea3e5a542a1469310faa0dd035e618ed6ba734800014c899fbf1d52d1ea21f738b60c32be6b5f62514b2ea4324f7a20fab1ff6cb0462058116a158e6bd8829cff694a8f97c7be83d787dfa43bbb2b2ac78b3bc7a5b6f00592b103b44a61fe6617f73d847826704e02f56d32d2ed4df85fae798750f7d4f84c2a81bd7f64e5ed473f2d61926cedbc98edf2a389b3fdfd796fe083bb41b6a75335c2f367058d3596d71c0c77d5a25379e7a379c2ea3a29dbec538275610a830cc29637bbe64f12f14476e24c33e28837ce1023e4b3ff1ca4d8e1ff33ca9d7a8bddbe57bca3d1bae605b5e6e959fcc2cd4adfd5650315faafa1d47f1db823353e3f7abf2a84a6db3c06015d30659eb5c19bcd753e51d923a32f7fa3647d96b0dae10e9e9b457d6f491b2055265ef9ad3a2b355924407bef8b21702dca87337bfe67fe3b4ad09b76f0dd5808ae92a4550e3a690f2c1702a764172f3ee6f9b5bc1b9db80e230a75b77faede302ee9775b1a34b6934d5aabae2634c168e32297a052b3dd7e6260e23a866e108cd18ca7edef26e82d73124ccc2afdc11d8a4fbb600d0c0f8d2b9543a3f170513acc1df8609cf74de002b3daaf230bb076f2769aad00282904165389f8ac5b9b46f1fe6708686542c5159fcd595e96440546242bf285abb3592f85fcab7e93d66a2aa0d8deadc3aa43b1cb0796a227764af407734fe2dd3caf1c8d8a52af5e02106216c5dfb8c4be1062706ff1cba626f831abdc1f29b062d6dbfcb53eb085be0bd1479187df0630f3eec091c51061a5f860365ebd3666749d358f66f6b500bb888c63346c03b324f5ebd5c816d8f8e0e81d79b4680cce353e03720d3aa591dfc5255239277022bc4341544081f0876c9fcddead4fbf7a69cb1ff77d25df6efa997535ac1df76d44da4f22280f6644811f2e2f8014ae614e4b67b83859e2ee57608691835545152200831cc9fbdfbda1984b976fa965cdd4274d550ce723f8fd55297fde0b146623cda3fc3007a36e7fa85a1aba61ec40269ff1bc4e8c6a0e322a85f22acca554f9be602440062389d871aea1f0e190de037f2adcd94b942c0cc9b2743fe8df0270a40a40774a67274cf0152c83e43cfae0d05824b2fd400e410453c30b72eb62a6ead4961660500304fc931451e0e69d6bedde9311151c984f182e84ef12ec640a2627d2bf798459808672304dc0d2e9026f2782d675c9cfb62aa80cac4d74b9b4f9ef8bfeea542fe7413c11804fb61148c9b479f5f1cb68addd45a83146a3926fb9b0c7affcd529334a2562e3c735e6aed645cb314bad9394d20f62285ef570262e641ca9140677e01bda0995ed36b1f49d9eece39533185844d1f029b912305fbb047a7455c2ca2137175b3cb3cf52052b9814adb2c7e3859943323bface809176407b3ddd6e8c79ec0f4598db4a24e4b41afa73b71d8ee078c8e243b4281eb4de41f370f861a6d25c1062a12f761c66f2d35c165801c9ec3b0631616e9302f1667f1d9bcc3345aab9c1061f717fc603348bab84feded35ce9c8c2ddf159807e54fb61dc67ce7045cc6150aca9ae762c308178f1d9d0d8004cd4cefa2364be649a8eca3d3dedf07fce4e4a7f12e3c71afe9f5924e503ace35a213dfb9ae0c1ebe2fe48ee4f0ad4cdea0c39e2f4cd6254518420a294c47fb7419f57c41f807bfe29c34c810b6731d1fb454e7d90128bc67f6b5731359c9e7a5bc02b198834ea30bc5d6bdafee44d5a447e68b11f5581cf07262b1bd9070e228a2e9ccab2172e36c7c207e27e3c6be5777c28b157d3f5a69c2f9d9595e8789af6b284a2e30bf268de91f798be1e4023714fbe67ca3fb9877141f7d768bf5f0c12787ac80aac664c9d156dec2f3f807a984f6517da204f51ff75ea83588abe90c6efc203d4c6697dffeeb92491918e0447b2a0a0885c38558cb2ce588d45a2aa9390ec8a98e273afeed886748c4492c7f83063f8369a9b8b9993ef7eafcaa28f247446996b01817174f28bfaf18b80da91d21a24c8d83a037fe00a6ff9b3abb6dfae48cae4c4d82be5548023a353a6ad8a0e5cc98924d492c2464a1a87cd688ca862f4fd506d1a0436ebaebd60ef11cff18021897843712d041ba6cafe8c423576bebbb20470b5914eb455c4a524792dc6e609b08242f54d19542089405bf3e26a85b2aa26b69afc18de0f8f7311559c22f89c9dd80c8ba34f92d94b90af4b3d7a3bf7836b17a6304e21d9d1a40af4f998284c9ef66b8d11c3188a9b4d57c0f7e704800215f0ab5d2687c008436c9df7466475960fbd26782b92a49fa65555080f9af475abbc07f7cb2f231e8cd200e322083307b78257a91ac6fc6bbd398c908fcfcf89a00426b95cdbe9d6a47546134472a73d49049d5e7d6bff4c164bebbfe8b29eb6a830648a9bd88bd01fb3f9b77f6d15e894f8ea830d42ae401c943677506d4a9a3b5432cbe34efca54dc1f468a99e25b41d89b51323e00c065d923b7ed8d9929637a07ac877eee463e0927428d9c6fe39afe6e771676a0f6ed07150b404eee9236817754c54855413cabb4e0c310ecaa87785e1e363143663d077305977a1f299de7629e1b0f0a9e79d831bc5123fff71daf61f71c82e0a2b06a026299df9f8e0c2bccbc334af15d1238065401d1edb88ef93eafa44b8fd05fcd59aba9d36be402a92c750b33c07bb62888c195821895a27fe867db301a690f88dd6de58225e5f8367701c91a6fd6731000008ecec7c397c9d9579ddb585b5789a9b657582ba602912984cd75540bc337a2048829c0136ed52806653cb6bf0ed64bbd50257671935a183e23788f3c3d9235d8c85da5946a76a31b01c90ce7e5681d4badf003a2c3292ca70724144eccca3c369794c065d3e6850c69981d0037599c9b46e64e088411801329fe8a7c292fea060e3a902641cf53dbe337d527113f93a05db3b81a7ad9c4b50ecb5725bb4bc740e8e1c6766977d4722e79f0119486887061fa8a3f29ae2bb39010beac50164e6856717a524c924f2c30eb28b8eb8beb5729b9e86912f6fc3a5a8c0ef7e0c7088fea12975486cd918fca45951fe3103b64ff88eb374ad914529e402b0badc9d1a66f603efbdecce974cc80c8cc510213022eff46097c91e4d5864e1b88dc2b6dfbfaed0fba4d1b5f44f4b5fa150fc239f83857189a400ef6c2b73ab44fdde6526e2c1bb8aa6f4736ff7aa3dfc70826ab07497fc65c3a200367b651c94698bef19c08487a935e7dcf2eb8e5df425bf6be18a2bd9c24f906698a5fa391b7c8c50e7231b7c52e96fe0fa9c9780ec12d25f9a279705a8615fb4bb461251539b3844ec8dd7b81b93693ca4427ebd0454ce2fbc2429e8c3f9ab128c3fa28bd780e0d983c46d4b3eb22cdfe5fbe5a0915bfbab253ba464bc67096764ce396946895aaef5db9ee07d3e99a3de7d4b4324f9e240930f3277c64fc367de9e553ed420c418936ab624c78d401a9f140c6ce29da5b0b10af8c9dc874876619df4702753eab3cfd006651c4d3fe9d096c34a607074ada01368538d7d0eb6291acb1f81c409a6e0170c8180c08cbaf33af25055cf626ee84be6f63492e4fd3dbe2618fd990923eb18af34d1311d7fbce199c30f74bd4a51cd7ed0b18dee69d47e2e64a379dad30777053c15f169d2c18dc318d04d828b0b5c1cf6cd7aff1cc72e08c3edc3cb5e407c25f57fd4277855b21ec43a8f3b281f7c0067a90a4d996b631df0b73735da17bc7e9946a60ae7d2baeea36f7954e49b4811e8e399cfebe6c22b62052b2107ffa5c39d8d85382d54e23147fc1477c985b7639bc507bb70a990f6907d379ac6bb64afe105e534558036302999dcb62b5f747e56c90e75f39bb58d7b9477a3254b8fe55936ae869b630e5517aa946db015bc621b8a455c78a14efab054f345b74a71e30404c497451fd69ef934fb1758495d8816d6326fb1f3ec83888c841ec9e16d74ed505f8196aebdcd3f1ed0fdd2501f1bdf5b9c1cb3c1cd45aa619f3324e762de7c4132d79e504b8b8575ed8bc6bbbb8baa982bbff9f35eb77c777afa74a803255fbc1f83357ca1a192a7dd31504be775e5354c3d1d023f2fb118b774147590cf215bd716abc0a77684367c58d08bc46ec2d197d1057b1e028b92d1b75784b85271cf8070bf56caf778ef11df54194c7bc050","isRememberEnabled":true,"rememberDurationInDays":0,"staticryptSaltUniqueVariableName":"e58622878c5b4107a5c053c29b821537"};
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
