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

        
        const staticryptConfig = {"staticryptEncryptedMsgUniqueVariableName":"9b9f35f1121ea0c6a4c7788707fcfe7fab53dc5c4d55f68d5bb830ced4f4afd274cd7c184ce08b69eaec1c2fea25aa44473b9a7a7086547984448645559fa2d1c15309ddb484aef08244c58ddb9883d2c0c0169990c49a0dcccd2fa477ccab095ecb17ea698704d20925fbccbbdcc567f6a7b00693aaf9861df24140c239273df53370e8ff22b8595b4080205e161080f3f08763bcb25e757ba8856ca35e4cf7401ca70e1da9e1efddd39ec0ce8ba933cde016005ca0bd577efcd0d496ad83219c197f9d493e3eec5c3b2ed0cb6916edde9569b80c8cb4f5c79f4928528b11835138315de87811a2dae21f58afeda4a8775fbdb3f9dad75bef0c0c849c3a39895e853bd45954a526cf19f77defcc2f11a0aa56daa6885856bd48adb2750861fe0e68de4e0621fed4d227658b1ea9a127cee997841fb6c1ebcdca485f8136e012514c4e2253eb2623341ae022e32bc54d6a21c22c61059b5f4f174beef950c72c401685295a9d8664abecea16ac22aaf52d959e8237fd16d175fed4d20d6f6b92e497bca2247746dfbe8cf37bcd70892d6c16201d123763a567cfc13fce3c563cc413548e2bc7eea7bd8faed714d08c0195e22ac9d0003525c3ef9d49af501a0a13f3cddebeac6e8b3bc1181af4ac9db41fe6ba36b45d05a13ff29e43497d4008ff318f94b7bb3fdd40c4e8d4978fe9521a3ef50bdc26a4420e71441f11691e3c1c59d9aa12cc8a93a642f8f94d354b0d592ffba15bb2bac4f63243c9f187cca1ff399901f148a0c38090e3833020972b025a48aa645b2f652028aa1bce6b0a2cd38de68701b8f1b7080199470c5ddac8399b0641d2548d9429526d30f47b8eedb4606bc34407b8cb2bd2cf79ad12cde34895eb0ab4d5cd0159544907c7ba22247095652d4ee73e7351c46075b260335b30a914e2f86551269f9e42b4740f48ba04114d9e2e3ef4b8b68bc729e0223dde96b74a57f28eee24497dea24b91b7239411f7638781a6dee02b81033d9b5569c7c973da45a1e4ee485a85637d7676ffcf3e28f99a8e3f2ec9744a1b63e63c0328abeef91ad3bd3e26f971c0be3aaf509f1cfed2d95c203ec4a446bb042fb5e6d2fd9b6e1aceea9bc1cdf105afc8e86daaceeedd1b6c6110c8103bd376ef9bbcd45cc374b06aea103dd20d0c0e154f06f1d4047c8e95c3e860846daf9c09fb975e91c532ca50d2423a2e50410b6f6da00fe466d5363ffbc79bfb69f1ba59a88be51f42da275ccb32043ccb5f2a4cd1ea6674cec686b237aa9609fe3959a0f832d03a3ea78fabea643c63947fb66241fbdd0ff05ec9550797c88eb0a7d1552c7d06c947b9c78a5a30178ecadd1f7b65918f124912f2ace61dda5f573a4c643e32c6163e7258ddad7d93ecf9b48d2270f5b1492231440dd822ca0b76477c195256e18f179cab754bec56e300bc39998cf910b5ce587f4f57256493a0d85e1eb6ddf52d688fdde279dd1a927e2d12c552feacc0340ab515bcf0ae684e27d5328490ee7acbefae148e8ba6d19a5cd30c2560eaa39e8629cd760051bc8ac53f881c7e07eca06af97754347fbfe0ce83227fd6f639824b2e1fd9378c84e04deea898f03e22ba1865eea28943c9929381380389872b10ee8e05922e36073d3c461b05c37cbcef466ffa5f8fcc37916f284ee3783cbf1d599d8ca1b677b559100dd88da7246859d0e002db44693b61ffecd8a1d4508cae6824685adc85a8f479d371d874383eadedb0479c0ea38bcc7a7eafc232612f7b1282e906abb1c9283ac0cb668c74eb5cfd3128cd4914a98b69f3e506a7cc87daad805faaf6e8a47c449865791d9bcd364fb9054201b53e0ba33770110abf8cde3238b59f97b5eb2b9da99313602b22282ca76dbd9744f57efd3de03cd8fb288a992a710202a9cc83d9435b10e1ce5fa204224c85d8332d0d44d62eb8f74ed836563256889e29cb5f09b282ae550f1a2c6a00b0d12e38a2f8e08f4b1c03d50086b06db490f2148ad308551959ac82fd3d82303c8c62b3bdcef211c4ccc4efce4a136461e27375f5b1cebebfc1ca32f041e5681875d94c4f6aa28790dbe75455133a56ac2704eece901b33b094135a29e890dcd32308b5a70e2981fe43a524e5f53b2ba5af18f3979b58607952869a9098acf3e1e180799f496445cc1c651d86d2a3571fcc57050b8548485d00261aefe42ae91437cf4c727dce5d5b5dfbfd6f3bce3f90fb0cf6dc8ac9b7a2efe7b93ec38c9761ac07e598ddf0c5a7fa324c05c94b3e15f71878a1376f31c58d5ef51bcb51397ae550b67dfd6397a79b6220fbee7d764e3b2bccac8928201dd828febbe5dc60d2e535a93c5f671bf1bcfba77f17844d49052daa3653f25512ce1be2654d26901c6282b9fa8a2b5253861a86dcdfb5bd88fb7ac958ffdeef2d30ded8341373bb23bc55f28b520dee9ccf856f3dffcb819849d6c507e9ebc1d01d32ca99e4c0d62aceb545db3dade8776ae21a4a464d151e66ee7b17833355e8e66b87588eb58f532e04429cc8c854f151370a3618f2da7f472e0a5c6d8f26feb0f2be9b1887396427352d6e8cc4511fc9417dc25df385b08ad8b4410c87ce233a3c02e0f4fc289e84577e643d979de45a6e95c1f1f9bb852583b39fbba4cdc524df558f60ec00085f4af6f211d7ae490ad6782119c1e2af3069d4c337d444782f87f28bfff2c95572adb3d3dd31a6e07b9168b16f1837c446cdf4d1f62d447b995fa8f0b965769c96f8f87d8c0e8a90580761186c522fb7f1d8bf7ac406e09a5e909faef23b00b5e22679559fd11c51a6e8499c6710d555ce3171481f03b8e7725c242f353c06e81bdc59a4cf0e670a1f0ca38b8e3f4cc77e0a46a29506135fbdbcd9737f5f959d86de9fb5471427baf5d1ccbd6f250c4cc1ad5ab89f16b92c79ec2e4c7cad335b2b89f2c20d6a87a147b572f3aabd19e264a631cb7c971cf633c616bf9320ac84bea435cebc96ebd23f3b38e9f57828f726d39455fb502b03669368e283af0705c226540d9507a946d544a4a20de5b150db13d3175517f261301d00b4fce6db1147db9cc11709cc4d66bac00c079561b36bcc732f56a73c07e269cf78f782cfe4a852115a1a5f0fb7fd19617bf21db3f98708a0f227bb544bdc7b4d13c5168c0e5c0ff3055a0b829582c74413f09340e761ad1f78aaa6993481805c1e15b7b7cbc4b81137011095875b41f786583303d27aba190e6ab17f0d1d2516c632e0cfba40b20b9894a5466859c025eb6dc6e7ef28576a6d644d193681a8126da0bcc2c5926db8ec863d48274ac509341359e9e68a76ccf4b5201379653e5611c0ac691b72eda3a90d3714fc871a35d67e0f4fdf681e28835cf5c416a45a79c7864ad2f481ff864d2eab0a16e68a60ef9be159bc43e832f5fbc7296d29d27e80f5e3f569e784b4fb881934fdcba59e8249e19797c237b3ab08b0eb8a611d4d2b7142e0edf8135cd78c74b0ed90c75a46ee2f8e082088af3c5a5b6cf001f0e0d92e3b81f67bf7c28a239330276651dacebce0ad89375337958bc2846b4b0de7fd8f1d5f1fa148be15149cf57268a9c4cba83dd96130a1635b79c08c3662adea5c04b6302fc1be167ce5acb1a66137c775d20525179f4c5207f46a58f9ffc430d3077b9b7ba9147b736914333595ad5b9e88627c50dabe2c9f3cded8345aec4935083a4f1606aa661ec370b8d71005fd5ee77acba05ba88a825dcebbd3383cca842304a24e8f15a0fbee9a443616330dfb99e4788e0411f894d5330c489c9c689604d546d1bd67f474652096b73ada03cee2bfd269fc199798039df2070b83708fe6435f404cc811eb2dfadcaa5ce592a6604c800bce2c162d779ec95063ce3e683f83234e5d00c9c047952222c622115943a104082a0897b632fac37c377aeb857680df3426955bcca6b805a1fe59aa442eca5b882396f95f3522a90716203ef64ad770d4879bf32c164e86a440bcb9435f514614b08790fa3b2d0ac7d99aff4593f77df29f15b25b6b95791aa15d829f83f44c072232b2307b5ec9bf188ae7f5f5cc8e12a84dc021d8c79d7ee3d31792eb18ccaf95dd881deda67d122a56bfab4d0ec922ca375b5e68995436afb9f2e7bfdf1a57f4c9c2bc42c492c0a5fc46c80fe84ffa7d6e54ff887cc4f2126a0c1cdb8e77023784a149f9332afcb48af695cc3916c1fa795bf3d7b1755a5f58e2e72010e86ba1b9bf4ccb877ea69bc3ff3ba9cef48cb6f6751d14d3c658b6a67672a0a564290db14669101e142e0082beef0cb8a97c588397fe5e59eba3723584be1dad4ccbe2f27aed3dc58708aa6d0e73a37144b237472c763deb6e2e7eb8df6c70bcf511a90d648027d6d5597ba6c9e547cd4b06f8d55d6e34e99838228269b86451b96e613ff73ac7b28581ca66601581de441a747a466383fbf0a3818c365289eba8a4a9b896b51eb04411875cf9ca7d29e398da3e5a613bf83be03b3f45d1f7b3a3ffaef3848c06114f5cc5cbcc5617ea2e2f523ab71b90d43f337a07507a73efe378118b39b7119925fe97063321aabd9907bbbf2287276a14b5d41f30a84f0dadcab182bd18129c393e71b4cdbd776ec4f6c23c1379079289908e3b0649139c5ecbec977fb40b11ed842285ba5a28d67a43eace9d459e4cd969ae48c18861680862e7370366b5ac6148bd4c2de1255c9845832b05a1b61f5a050cd1ed21c371d66d96d6361a962f83ded0654c6bb45bb826c5efd22c45504c8567ea6abc85b6dfa2c911be666c36ee9d63f7c7465705fdddc56da74a7bb32cdcdbc91a82690968b651a6b6ffd8fdbc1fc8c1639f357031bc10b17ab32f6d8519923a0df20c2b6901e4f481058ff99e00c08719907d64a61bcce42510151ebfa0bd82fa40ead00d0ee7625f1eb9989fbeb25a4134d7213bd9bf06cca77e2e12f6f9b05b3c086055566447de814720108df623af62f6884d793767a8beb7ec8327bda583971a6cad11f30200a36a113a6a71a9dfcf9e8f0f1d3a41c687f8e182947901f4466b706d1aa78108183cc5cce3be60d10410c254985f84e5f5dc0b9680189427ee3510215e5c2c1c52211c4c93ecadc239224188aa5cc7ca4ecf473cd30d7f0f81c9efa271ba215b068f823266d26a25fa3b5f8a3842efec5b7beeb6ef038601542e04dd686ac06cd33205975e8fcbb0510dc08a7c2aaef32c0e7d6bb9697541350681373e1e5de25e859a0440a57271d34ff9088f0c7bab93d9443dce44de389633e4b1ade327c40d7b4d83187b73054699d87808bc3ce09ba994e30fd3c43f2b27f90ed07a91d8649a9eb5a52b4e31cdee130f25344061548cf6ad408b1737ef559e71f408f002ce7e0ba90aff76608e4bf9722ff974f71cd70755dbf79432fdb598b80e66b880971f4bdcfa9a9c6fbbd974fb6d4fc68c48f458184b04dcb7ec883d868304624d1f9669915120ef82593cc7ddb364e6516984b4df9adc0aa66252dfb7d9aa402c2f3d38f0b6c06d69e1cf4e50d6d5e67c4cc4a11b907d5155afc983a92700a59848d0040e5b1bbccec606d2a8b9561135bc909886ae2aa47f5d4e4be0717b9a0ffc210b9ec691fec40a40c5e4259194ad4e3006474c09419f9ccffc4f5083d3b825465d376b8ffd53f8f4e6f24332d6e76c4c2806d1b4fcbfdd0fb2247ea7e7b2406d6ae9c11610b85443c1de85c982abcb3dfdcff9a00f0188032a68b71def47aa2cceec46728ea744bae923642f529a6a0f2327acdf542831f3752d10558f7e2c97f58b059f42cca219cc5226903164ada72393cc0bc41af577616dbe8c1fba2a3b61ac6b029f19291e3dc71db40f2dc5944a985e4a2ffc2fc3d64d45ee29a530583e71c5085a76bd93db381fac26aa632e994ff30842161c17618e6fa74ca4e15b138c6a863644262f02fc49b3707c7c3dcadec29e7049b7d18474134abbd738763b1e7001b0c2443a93a723d8bcd95bfa988f7d99e2add11e4e1781cc63430b9d6be9152343f76950ee881758aa34fa52e1faa7573e9d48f85cd0f02536331ee15d4d3a67c931259734a52214e98b2aad233f1566d0e8c5eb9e0907c7f5d925ea81ca28b10ad76a6828d177a47206e8c40621448990b71194a602a54e6fe87b752bd2f797067a1a80ae5a549cd01a6645bf482d57d6ea5ddc0287ff9cc8bf565cd531ba4c28d80de1035e67c085cf3f0fbf1a8091d7a314961f09a87c7cbe8bf3b9379883ac8b8bc6be421f8621741febc7b7bd7d11faa541bdb0c353421216bea8d3db6fecc1430ee48eefb1c9c1a83b919d1f040470b96b409fa72a42bbed2734f9b3f13330c9748f25f1299e195031ae9dd1394faff954efdae9792366777e7cb3a7529bb9e86af6b47b4a46e1fb7b823e7406e7d5dc401b79974b1a86a82d1d862b4b76f27ede1b705cba5c96c314bb58413a2a2159152469a7aba6b8114f6f722644a9b153361130f5d481197e88f50f3c5e9d37b5547c0918c992be95e64c3fe74ca987ec72e2576be7cc3e6145bef5f0e4ed96521c3f4bc31fcef7c743ecad1101e75edcf53cee080513b026886517bc11776e04a7b5749675cec814356092e24ede212851c9a01e09b977f06fadbd8e06d7ceb3ac4dbcb60161f5f7c1c2338934b5c507bf665323e7d29d0a60517fe259502b6493a81ee9cf80b681d92f5aecedf4b6c8958f0dc248a9d519c6d13953b94f3e954f4ec87ff45c0e6d6ef8a3547500d9b4d541e2e5e1217770288e5789d5add918dd1d1a9ae498246cf499fdc5f0279328dbced93bf44d84526a53e13c992aff0d23f17ed08b47fda430abf9d45bdc69fa56276a1b1fd77448fc17a14b1e1b536826d9d3dcbf7949ccf649b95792b09ca3dfedbc9f0511a0e4b1f9e3132b9efc24560e3b3e268e35edcb3264f8d141a8f171ecf5c0f3a93eedea1e6fb0d7bfbc3c949d494e30d821393fe5d868863799f69deefb1f518a31ebe6c37ad08d98d408ce985e579ec994788cb0d0aebf288b43a90c778fbade435e94a8d5b2e3fcd58a71356d225a40b39a09d91cf42f2fe597b4ed6928625f8a6b801cd1d7a75f6f0b1ed0c40c9db9a37db79cb026bd09770caec1d7a615386f1941480daa471333451162a59b894d56e4bc0e1a430dbdf230cd3386e067a801c5a46eb1bb39908038596cd55105602bd1a8cb909492731c2010492b2347900b1c012c8a5c3b143123f41c93198acf72e7006262eb95a276884d12dee5b8bf72d4178335fbb72081a38c58b91bb834bdf58e6551850e5ee859842e0e8236f9b78441ba35834e2842c4065bb2d43430903508f7bbbcff23d7571757be8cedb229c02160fb2708bf36402449b69ca5a8977f3b797ad1dc1c10fb21ae285d418ed2fc17557cafa8ac9e6a13856bfbcc2a62eb8cf4899bd55abcbf8a70eb3c06f0900590d11664daf5b5406c1277f2389b9fc1435c96850aff21ea6f18b7ab2334ce7b89bb8ad4ff3f8614bfbc7a93da17ba60d60931db41bd563d535bf79d9828dee6aa06e80eb8cacc602f7bfca31393fb5f3c0be3ed423e21e325345aac081774e402a69deb03c9607a362f5054c8558e5b42d9001f98794f2f779bce6d789013032ba4dfa2349bdb1ef4222702e3c3201b92c0622b457f242b279b7be79f206c41e2a813914a7e920c467fa1f349c9680ba8b82473799016cac0edcfbb97189daf905ffc2f400851b15db648fd96ce1ac34ed97f79b8fa51643a362bbf518a6b9e100d424ba6ff76069cbd4b954c8ffc8cf2c605e243cdfccdf421515828589b657309be934d9e929159d3e09d2e8ed78e2fb3031e6a3424f89c9081f4e8761d2bc2cb4b6cfedf524225d4f072ff0c72daf0bfb0145492afe54f2733b6393a578f3699b076b3a4a62940860b072db229542cc673ef2ea1596fdc6d9d4f89a0292de892f26667ae79c1aa0b73e13e91b673c46965899786e8516f6be79a435e9d78c69deb77a100d2de11a4158e0e646d25ebfe0a60620c137c397c3f78829f7089b00066f738bc19519fcb18b573184d6c23f26b12a824fba0d2c706744c8ed1e7c25786d5e0e1db48ea8cc0ca72d057dbd7aa94ba0926fd7a550b0e742342d40253fb3c7af81d993e4177809cabe76950e59f8e933c67c8b99c27da2f19e4ea3140d6bae2ad3d6629fb2dd095d122c1b97bfd7196b800f7eb48cc689679f4e9d5aa651a64c5577759e80473a274151b69fe9d357d2161554b93876fdc00a614823f0152a1ff9596ba18c113d150637bbec301cde6038e25b8805a41b048eaadc61cc6871ca23f8940ef6ddd4bf3a0ebaac0d70631ecaea227f6cb10adad458caf0739585faf9a535e8b6aa008872b4bd755b38a5912ce713433d7aec4f5474819035a3117358baa8728a183087f581486592347c55650de2c2d349ca2e1312b13d393488b9465059cd4773f1ca1bfd56937d6c1ad98de5b3a3d12e3654f11de60661f5d2172c2772dc0170d309228fd934a83189b9c8d074b3f3adcec1e86c8f349f784d054f386aa4a6f7a13c83e9212e050514f9cc5342e747168bb8b39ac721dd992c4e3f8893aaca53226669577f5cbfc8feb6c01b61f551975685194cdb5aa099e61cdf3d0b350f968431bc203c5c21a158c53bba6ff0f03dc8caaf7e08d458dcd8f776464b6e906f6c3ee29aa91f5ace0fb3d0527342da5406041c07f0ab1b9eeed316d180e57cd4dbe78fe8a34a09c7160ff46b414db518b99234ead87ce80ade25f1ba258c397850c37e7513e5cfeb632cb054313cdd06fd1db31bad2df31da6e2505b0244a787df8bd025b70ce1343eda4fbf5792e9b5790017152665bb589460cc6032f4628bbc124c60a8de8281b4f3ff6fbdc3dee74defcfcbacb339afd977e97c3069990e084f860ec0d85141bbed09d56e4c4548a4398dd22868e298ba0cd00082c1aebc1f56012104301c6f7c19fc098335509f42186b3ad91fc2cb3f5ff40aef34f01adcf43014f58a4f408625d8474fcbcc2f7d6a175fd7d64d28507ce9f5a9574d7085d58f5ee56658cab4152ebb15ac2a5b241d413283f39ccf7ed74dc36fb575e2c50e1ef599580883c1dd5cf2ae0d0f9048fff41bad4fc400f8008db11aabc93937556b8da7ab9004c02e7277867516ef2dc0c42fe5fa76712fdd7e5ee16448d3feb59bdcd7b3f17c70937d280c6d06c9d2bb44ae9f2e70fd5ba311f80ed45c3fc9807a8d66269cf0d2437ff2e47183e7eba368616b8e0203a4974cf54830cc38de777e1d8a69d4288c5c269af5fe684387d031e0483a35627caa9ee3e2254d2c23bfa58b349ed2c8cfe0a485dae105e9ca48676af1e2a2190b5a8fc894b55aa4baddc5375dd2182405abee5d7d79050c9143f8f68eb4b8658a5cebc0748ee68f24f3022cadd090c6cf31527b032734122cff72621113e0cf752697166b891996c85d14249ce344f138c8ba1f529724e112eeb484a034b2896816a208dfc426beeefee5f0daab822c725b0d55f0528f76a3289e301ca8ba0024316227f0474c2698a487498946b0a6d0ae9d50fe468295134aa030d8ff8a0fbafa7cc9c00e17d410b5837d09071ce541057aa448d1904ccd9af6a0c3929fca53a744048bccf163b3d9432414ff2a4f1e28bc528e68bcb0ec97f267bd474b9f836aa1f6a09c87619798429b8a155044373f432ccc7db9121b0511b3476b63bdf57a17d04c4036d468b3f0a336728a3f93a7239b666ee1f01b3da6fc169d9a30a3dcd10d55da74c56124c69c7b2a4af5aca84606d9af2a5da3bb5e2b3ca088bc7234aa951e369c96346197e18ae7b659c09c0c36a491d644ad06744bf5886241686f4d250db006f08eeaad7b6ab10cb66bfa1797405a471b252495f4da0803a98a70f81d5dbbc20cfbe03f1020ac99070f23321d3a59198c1458d97b3a18707097268e9e528fa648ba447f77595d04f5c916acdbc68024faaf3be863ea182a70ec38d05eeea4f77f56364f84ee0697d75437318d8ba5995e1b1542b4f1d84c751b2e7dc6d0b5d249a758c7c96be9369f6d0fd2c97b06588f7a6e46584e15db6fcb5258c4f3f5d904f114e85db515d5a5199e01ab366cf05e7b2d7f9cb202920ad28c903b419a6bd4f41d8b3419efb5ace9394ff4ad3c3ab82f63e38245c12d64ca521c4a3381c665472d54014d213332ae9b97a2eba70b225d55edfca15850c1a6f155b1ad7bd5a3fc98016bef2a72b66719213b4749a2881366b45077e4faa73ec1bcac675fffd6a004329716bd1deff04303daaaf2c253626fdb89a780f64eef5f3c441d5e51f8d1f5fa1b1fde1d26182b1fa718b86fa84da57482888e4fe689c56c54557c8654163c89e2c845da5b67bb298cb1c9a2a6055a021db81f6c45f812c06697f2f5706e724ab5f93f45d92dfafc9aeca1033a905d2e4d6e726b926179f83a8ae6d3759b892aab83315bcd653580cf228478e83cfac2d39f4c3af1437edca7c01fc0d1575f8cfb4112952540e6772f36e092c27e1d5bfa7addf4f5b7127944ebf2472669449667789c193cd6b3e96dddefb573ca47ede12f851a92188c1125843cd842b985ce512b0452b92eed5bd68180bee5b9e95631d9ed434e55f1065b8e737ece4133c3890e416ce6af9d3c94e55242a43f3b9f44b23c23df9cca04d509ac1f92b81810fe385866d4f9db3db1b0cb936ceafef397eb70af32553a4cbe4972b952b1fee72c4784b9beb52abde2c8bad47ef7a29fcb29bc736f5c1813012d43271468487f90fc59f9bc754bc26dc749a44ece336064e87e9ef4ef0a37f7a866bc70b4a65d699835a91c38e3ce16477c8391922bd63edd522f29c330ff620e0119405852458d38a9c339290686a93c5d0187e5639416b211729a79db7d3498f36ae4aef039ccd56f8228f8077e397303a844ef73d84cee08392caf312b788ad1a2029c3949819809220648d798bf6dc93229300e174543385619d4eba6dc484850c292275f5bc501e566022dd4cf3e2f08fd389e0ca44820f17442a1240127b3ca8b56aeaae9108e65220bb3171cf2b02d27d67cc2b19caeb6b33a36d84f9acaa8c115bda00a56c244914025f627c6a7c1eeef302a272577681c10b472ad46c58476feea9584ab16dce9cc488356e5d838c1fe164bab9a828add5b4c73b0c4555c9d82b0ce4f78847bec638158cb1c72ec35d22d0b4597ee9ba3f923d68a382f3c060e31b114f98eef5e117d61a7459f00abedbe1e8b62689d48127a369bd09ab47f77063c50e6ada4cb35b2a190810723b8a1510f9dae7ed9be14541c30fe29bd8587f0e813f5a0cfd9e970730cf64ae4f795f7039538d9703863cba2c4ee8be6727db15ce33900a2614c141ebb53c7cc6eb421f2da6bf31815a64edc02bb2f9c670fcbfd1d8bb0cc8b560ab8cf169607aeea76984c79b2b59e494cada64d01f1000949f03720a19c393272b7ecb52b6ff8978206abf6a6536368f09ea01b930ff4c88e22ce7b143367e031438f48c90aa412d07e5a6897c87d3b1ea5b1c1a1c931d9f9e7dae135a6520f0446c7805006d0e340298a9f3711f17484b71c466d427d7ce6dd095656978a8d688261335822a746f55c68cf99121de94f094b5f69c93bb20efa8c5e0da91d403b152ffcb57e5e870173ada8c6a253a0879ae948e20d5d54b9a63db28424828a4000547c44ae15b4c83e0bce4b1266c0fe1798cc9e132b1c9610bd116efb2fd2c70a66fe69856499c76e944ef514e23a4ed61e431bba58d70db3fc2b63e36d3f30cd07ed5f7d79b4fd4d35028aa19b837b163042a35381429a7367594f2944d9dd080e697f21b508fd238db632d3d4e2519ac7de7ab8afb5db4f60160bb515be68446845eb873e1cb11cd6ee6e34767f9cfe54353c589243cd49acf62d2adf77f2cdf9f98768e859866fd7be73152baddb5e4af9a66b1cd21c441f082d49ce70c13624d00a95582febd69273c790c5865eee45310d787e89837764825de654e527300e70e94b87b23ddc65ae759570b84e9dd6a5d53f6afd86427d2576b43acfaccdb69e634b49381982da8a7aaa6e42d9b9b15cdb7d022969223b3b84e2dc6982b2e993335b8dc7519b7ac85d1cc1c0ce61acbd9967fd4382776d2b08fa27364c9575a178cf2dbc6676e29d9a61847a9cefa6e94c8b78c8d69122b28332a8d81b36c7edd7adc0ab3c180da3fe789e3d7af1109c61c320ecd8fff0b0519abc8931edde2ea91626fa5905be36fae2d2104f16d8aa3adc845e1ea29c3fe1c1dc2469045a9cde75a2e5e3a74d8eb3c9fcf804e9a8e57a24898d7892ebd408863f148ff814a4b66b886f5fa941c083cf9129e57400b1d218d46e4c42bcaacc813ce9442e8bf9166396d2cd8dc274eaae8e8b6d3bc59fcef96f71ba20531d6729b8bba7cfbc8af03b24c327e24dd0198074cd487b176d2e406723e70bd1b12c3f69a3d1d65582d87bc6a00119897c4a00fc273c0aa3e644236b3814d8578066cd387e2c81a81ff90a598b6cb74539c6df830696d2ce11fd9a35dbe70a4b1472aed5f7ffdd3af78aeeed4732fdd60c000d2e480cfdf0b989953b05ce648f41f27bdd368e3e8fa0250bfbc83956566caf35ffca0e0204ff6007193447646e4404243383030fcdecdd6e477a7457e1e36b0166081e9a73deada58a53a31b15a467c3771b05b6b2d594bf1de8afcb6e881d403006ccc04a828afbe6ce68a842f1c72dc75dda8756441c8c52f8858acf95ae65cb4c27f0eed6eab0dff432cbf468175cbdb63c530ff5f5425374927f2b25b2f5bdc9c50f86438a67b8c4c947488ad75a62f1aa1bf6750ab491c0740723bfe19bf53d5013214daa569cce4198a0ae993efb151d94b9bd071c378a7c46304ade8199548910ebb43b1497aa68d717019740bb60b203f0421c5306bd2fe656577951f4b86bf883a3616e9c1bad9104e5e99e3af25f90bfda7d4506b988913bab7286c1ea53cc4ec3c11adfb9be0328903aa0141dae597b56c34de6bad1be332a8a1fa353497e5fb6a6aacf307cbcc2cfef2d30ec0467ec3e6575eb845a7dc0e64971012ed289ad875681d4701cbdb0822023f56cc4d1ce29d04352f2f89c701591aede9ac1d8b46eb87b3f5870092ae7fefab9048c6c22a9386f80e60b6ee214d4a9ccce1f128c464f938ebbe235682c1e82de6369112fca36da7a43982de886d163fbd2b730b9682c7a9a747aaca8c0a6cee2bde06643aec680e605c428b8f6a68d7105d8c21d0743d5315b0bdfa06d00e4bb262e9a2899e7ca2b2bd265f490c97425add36c60568f519291349ff887cf5fc3b6899dd1743ae6d64722c2b1534bea2db45386f34b53e75b8031b544c339fa3b75b485d043511155f48f4227ec7c9017ba1ddd3849c7cef89b05be52030d44483c4b2e2ea048733c034991e62699d241a4e95809666c4f2cfae70643762ea8d7a274fc74c665266b0a116cc3f736d0bfc0451190827c98f806bb41c3f96b872edc5adeec1b6b088a081bb17c8df7061b6de267a55565dcb7cecf177340c04e2f179ca57fd5ccb3cac7936a183e98f007f1c5d83e734620935bf7e73078170738552f8065323b502b952247bc333fd59c29f58fb9d4057e5b766294938d503c4621e4602ffab90ffd0ac0fcbecf3b85991d803f58be047acca3751ee8ae24813ad7f3fa75aa4f8f3cb7b9e90281f9b13a08e441da6cb10f9d70b8b75e128f78e59b58f6300d6fd39c4fc378eb460134f690e02f412f87252874b6556a8efffdc6bef288ec345e11e099bd85ff05b372966e7e6202de7707edcfb19e8ffd9c7dea4a06d12d326d06b66bd873ecd6da66ef9e587125a8ae93b1063e6d2bc3f09a938bed5646580417fe78bcd3d53e974a60f0c7220e549d5c45fc84e8a03688daf7120ffdd2a12c4040dea9d11146e15676652b7d06c0716cc6b21cbd18c3bd19e2465afc91e450613cf27872354291df67e75c165095b3a951260a6f32031eee339ebbe16c7bef58f132059bccea910a15ad475503c0b03d9d81e9217c16d9f7add337529b115f067bef6361d327187d5a58c58a0330fbbf83048ffb6790eb122f034b89c966eadf0c24c26d0c113b69a36e15ad55e81d42c4f1010a1eb6b65b9216d8291fde58b58ac0e25e0e15dd5fa289f49e57b92fab783896e65febc8ea6f31509e85dc6f56f4d4a91e22218a489709c7a1f483609a6a4284fdb4c9c18816a8daab2c2a5cea5c51a14a528767b6624780d8daeaa9fe914f9d41ba953c689d056a46db5365eef3f5d3ac3979a54668f8ae42b977edf560be26b456ec50260c292ff466a0605c188b021b9bcbb0fea61f308b314a12aa26880efdb541ab4d943037705787d1756b8d98dc8b8348d865d43e4bc4d26f94f5367023c960d04d15fbfdc486368e2c6937ff9c3f8309577b13ab79289b9d126e796579eb4ea6870748b0f1c5a5c7690175e00fa78792c8aef3fc296d8abeedf2686dc630b7236d3e8c8d47f5051ac4ebd95e64d8b6bf54cd3e95bfda1410451546a55c65ef8d0c568aef31e11e45b5adda0dbce335fdb43cbb37b49f871376db359910b18ddcfb29e2bfb30a0cc61ec9cbace95b6252ed157408dab9c74a886ab0c10310c1f04f2d38b615ee079aa25aaadf850600d006afd7918e71b39f15ebd1f37537abd63b8aa2cf25d08048bcdeee717dad4e703417ed0bac0ed9eaeba01065c862237e1c24ebc4042565b6470e64aa0fa199614abb4d72848dc1ade81ce9f07fcee7097a60abb7f3bc705445d52bdb0c28738955d832cd17042865cff3f834ac76e11b3da9da78edda1444ef6c8c4e1bbf1a34fec28388d1f2b38d80cf60ce51d7104869616115d65fc651986666f88ca41ee3bc2879a473aef4cc44bbf24eadb371dacd8d0233af28cccf3bdb62d1fabaca375c6d8eca6af83e7d70cca7f84352917a3090e61098f8ebe9e0dbdd568e28b4217ed28d5a83520b011cddb1716662c7c38427b14f25f41f14d22ac8b2cf4aa50960b15b97fbd1ac55afadd39e75323ba0990ad7ec6aac8884c11c3d4dfc125255bf945c2982511f26f6b41ea9c43465b984edd62b20f311b1c51f459fc1eae63651b56da72d7b19e1e2b4f2f0aa357bf0aa89a8ef0ed883439050f3c4fadd29d42e61711d9738411253d90572a8038de5d367c138e10b509ce45af21132d021bdc123453d2553716a10412f94be3f0dc4a3b79b590ee400a64941f5c51851b30f60667bac6fcd257e7c140faaa1aabe5628640716c96ff65a5313908047aac733b5a8cc1839e8390d11fc55a5d24b484e5a061360bf05bb0fc3a456dfc9ebb760bab8d473329bf5d37880d5905f21857700171728e93208570e9297508269c7279c82e39e8458cf370f003021621aef474143df1026b5826434ddbae3a632e6d2fcfdc73b55397a2fb36aa9ff684f8110892016fab83b2534419ec288bb16ae2a15f4a75fc71db179ca9dea7f8ad572e8656be088fa09b8872dd4ec8d8face6d0e6adcce1faa65aef44c28523d3ed876d3ff10baa2a499c672d4840e8ecc0444a1c3babd7486dda5e7b2c3cfd1c444fd2ebf9315b9c94f561f174978dd5c9ea9379a114ab791da157539e195d847fef24e37a65a3171447ab98c831b01740e3bd25d164ef927316fc5b2e64a97154aa9aef25dc9b537172ea99bd0c911c160f35c3a75cbb306c3f5b7ff698e79c2226462f9166d0494784471c29a94aec23d32c30150d0b855617b80eb921c124a640326e4d2c83f8dd0885966a75ff4ba92a2a845b959838042616d0b2532e36151efff2c65477f1074c0ca69f5fedfdce5427d1b9a7df15763f93bdbe5714a9cdbdd0b80021c719105128e419516cb96f5f81d685d69cc2e186f7c9b1f6baf914a1179474dd5241751b7c230582642ca6d8ac76ccea6d6e922a4bcba97151273f2f5a02c9ca49b15f9c593c281951c4fa5bb83a474908c270050f2a2ac7eb850d890b71112d59017cc954777964ce5470e3edd9995048bb3e305b474f6271900589bbe1eaffc8b7d6b263e93f6b44f20fc25d46c3f85030e2d21d02e6b457c1d17b6dd36b28c9129ae113ff20074bb9ba651f00a7bba8843755f2dc77efd42f8bca83dd30dd711939390d3a426135423bd9f6e3e50a4c897e0c1e2d2b4747fbcc72ac4e49455084c6ada72abb5b3ed6bc8e90d8168e76d4444109a2c3c46c7c8b860d96fbd060d919af951aa8545cbfdd45af38e073ce58a8a57b24bd73dad13140cab92e6da984f93c34dc275e9c8dd1743bdbf12c5beacfc4cdf181849c561b91b1134f2e8cc9c3a7539562207097bbd853dc2a18de3d7b5412c9cea0055f5fa6f36120e1a6f377d4f7e7ac0583b96b0c96ea9e1a2ab6414dc544367c0f990d0a0964dff6585172c4081484ce682968db0ba5233a3106e52fa6526d2ce921062427afe592999cc89ba8313f31c0c5dc96abe7deabdf10d2509df66659718ec3bb669b0bf5bcdf60799ff3ef59f0ac290724f3eb2bb13333f4fb00bc04f5619adfd1b90bbcdadea1c8b4dc57da4c8e5b155214c74e27640ac9ed97fbf53dba3cc2ec9ddf74184341b21149735f24b0967a51c66121a918f07b60ab8162b995551a4113cc1fe0d2019a64cd99a8312d12d1e0bf1ca36a4102303101be52187a549963b210a2e4a8d6e38ffb97aaab6be282ac64efa33de50bf231e6c31cef9d2231e2ce581a791d2daa9def7874a6a997c61762104908a336af6a3c37285b34e678d1aff6c3724e339564105ac932a690fd1411a72052621f64fa2493583452c0ca803ae5c222c526a2078e781adb54c4014ca9b312cdb24d1a372bdcca2f7ef2850db26617d5b519875d7aa7f0e55f2b8dfca3738fa8d3506eac8f1ea10fe5bfcaacedfe1a4ba3b891beba3d3491e53fa94c043add3f4634e6fd3d9b40ebe34012e501e4b8dc443839bcf3fdd2968f8d455d902570700ead81be7e1427ea569fb11fd3a62f95cf8bbab177d93f89f10797b064bff05b5efd3047cce5b141fec66db134bc1372bf2ae5cc2beba3a386f90352892552d13848fb9052947167cdbb2c504925ccff2acbc52ea45cb22d17425eba8cd3847b875a05d9ef6f98d3077ed109217a5fdadc8420c4c3e1f630abb53440d6540f60456f8f15bf5004dd6ee80dcd66885cc2116390d25c95594aeb7ee6c890a5a6de39ac71d2e7baca5b909ddf2c76d872210bd9b267b697acd537d44ad279e8c8c4ecc3701e6c96da4cab0bc6ba5d8d2d1eab365d74f639f13d669f0005eabea5dfe10fef03fde631e65e8e418b7a411b8d0cb40687b4ba447f9b347cfc44947296f9f49df40a0c63b5a64a9bf047c3fa7114be9614fa3374f1c595198996662b3569841d0223b0bbfe88d92021476cfd346374066c412adb3eec546f8cc6fd9bcc8214c5036e70107a4efc5f50d8bc9b6d3f185c26e2acc4037c868cf4bcf79687967835cd5076ae30d960e16304f3951f08101e5399389a0fb8106c952110fc2ae2c9acbdc0b58061f904bef3a6205d66cf4fcb4908a164fc06f7c1bfc7c5bb0299430f53c35ede64daf44577eb7f61981ea1513a42996e17ecab3081d9509b6fe1e4ff114891262ac985d39c5750d0caa842fc7b7daa8fc27ae497f4fca075e579080f0d7a6a64a33ffba9a03dfc2077f00ab762d6622de13db7029c025f653e446eedfca8d27006036b737fbed064dc745d99e09607fa73a02b5b9c0192000c8710578227b8cbb70ac19ac3e0bf96b51ba9a92116a7340c7cffdf63fc3e5543c90e2c327964bfb0792d7e341669f7162901fabd3d67f5d3e1fc848ac726663dddace204464ce40ed3f420668a3841be87c747fc6218b76a9858f5baa141917332e2b4e299d3d2047fc424a0ee0579ecec741402b56928b1134940f48c104c8bfb0a9c8ba23a9840aee01a1a91daeb72b169b7fff859d1fbdf2bb0e85065a9270e04392fda072e76497a40ea4aa0c6b2d8bbf56ced85c916de82b226adb56632fbd73056b2d1f3705ba3e4f8522329084e730c945e9e304b07b69d02b232d48304fc40413c46fd84e196d5652ab4b14251299f5f45790c3e444579faf080cb95ba0e4cb2998cfa998e820a1655d8f34592b1c69a8c28027a30a68f22ef11207af8384c1d016353cd8c987e82596fedba3d08ae371f2ab9bdc4722dce8efbf4ac8e581bcec095ecbe52c79e0d1a704be056de360b163dffc8fa3bada9e1a930db52eb94125d893939399aa0c07be2312517ba43f79a36d8cb13e1cf4f715638800f747f4e9e0d0c4aa76774ff492debcbc76fc9989e90c530aa73ceeb4c601099a8f847024c7ac0de2188f975fa19ed55c72550f4f61cd750564464c71293b5566168b22df2bf195d8bd33399a278a5ac04cef030f1ad4a438d38a0fdf250e3cc037757acf30a3f5b2e4e89366fdaa54e8b0c09dcd2ccb544e7afdb7706e4b294547ccbe21a1bda7ac97c3cec29e3cfc11abdee1117b975666881c3bd72e146c20c2066371452a8cabf939f1b9662e0f9e92fb41c1485e3d8d7a42bc19be6d7dcfca7c819cc35630514457f1945d0467036405d6b0c961c33d2d9f6d0c64e8a919b5b89377856ce8d0c7901f4d93f11c35b5c57beb44ae3bfb3f0975d5094c0f29afb7d24d28a9abbe0737951739f8beb8736407a3edb91d2bc4638d124593e77e6982a4d8c6a09d30c25567adfd0a7c6e05b4d7abb2627a1239912aad204fd74f1b19d3c48adce962a2f86b5a8df1d7961e6f1b695bf7da7073ac52a944c83859eced8c072c8f708f4b076771b2889bd3f92049d348abf20a1dced36db014a7df607abc87c1eb3ba3f26737310351fce7e8355c98800ac2e246628b112256b0d4e4c24d875318b642e220c775e5d474727acdd0d95feb1e46879e7acef6a553560d7431c12da179e35f0093ad1b5032a46739685703461d6e70e0792d0f5408d745ab83c14ec9debbd6fa33d904c630bce53c8e104ee690757d6b173bf111ccdd4ce7e39784390db289af30d36d960647c062a0e01a11d9f46737fbbe2f671e27382c4491c4ab75cc22441eb343cd1e9fb5ffe50692ff33ffb583933b779829ff20cdfcfb196a5f61d7cf0eed068360933f6925d39805b34fe95ebe586c6f32d8633fdc6d8ebe57598c514f71e129faa93d9d3ba4852d3b013e38eb7d85bd158ba5a41fce0d5f49d279ff3a233b43846cdad34cfa5be5ca57f90e8665b29902c3e52086282c8312ba4e2e0a22cd3dba293c3a97dac5c15cc7aeaddc0324018f83277d2cb88c12d9562e96ee3869ce9764e0d79c8936e8b67d396711089f78d3e1e72bbe4ea40287dcdd27e46a6fb648d19bc0cf1d945e1c43087b9dc197cad78d5e69da30b050f5a2142f3d6503050d467bb012d9689f83a3381e6f6b101611aec619643f9d8e6471c377c4ae8e9b2fdf9154a19c31bbeb5780fb22968b58b05848145f048c9f4733ccd69082ec98a488918bb7f1b37b645c0ce8a015aba5aececc48c1107414f6648bc8732b3b82d304e707dfffb355448cac3ed307598c54572bb9b5bb2c57cd214168d7c6f08a385c4b1b3573593a7449b814ae01b066dcbcc84ab52056445e0a103ccf34f22d833131b6a4e2ce6c05a18bedf8de7ba2b2eb927e1fbcb7f4d4e248e1b8d2428035f455f3a064082230b1e69740309a3c05cfbff72ba8c28b66c5a27eb59acc1474f50425b99e76419eaeb77a3c8a0fcdd0df33a2164e4aaae37352bb82819dfd8ddf388a422426cd8bf2044d0fba54c445f4ef41565cfc9eab92102c024ac1d7753f9f1d572364040d297719ffb06ed42973c0c127bd2d7481ab363ba2531eadfb117950e14ccd1a22a6b067f3c649d8691112f7ed1f57152fe6c2d0b7edcea0af4a82344365cf39c0185ca5229157b42e81be929cfa7928ff8d33aa6da8cd2cfd5dec9d901e0ff1102d600e29a0460fb7a758196cf49bc2d947ed8648a6bcc846a189df97d5f4ca2cb7200b57a4b470afbd056abb4cef172044495f56c24d7a0cf507c9345ea0f1edfeceaa9ba26a5414a08555977e3fd88e407cb745991d91dcd81e03642154e5d356edf0ec158a7606123c55b91ed9c7bcf4ba7858e1cbe4bb7e4af0968957a71b8ac40267d152e7900146b4fc3173e0e0bc13e3a2c5f670eefe596a7278e08530d0a04bbd8a5ebb9fa1b543aeb70dfafb1fb7446e0e7fff8c0c0e547d8c5d99998bbca10439919f27d074875f2ffa040f9fffd888ed8f4566d07be14552b4f4464e47ba601a12830810ba3acac45693331f6a7518ad823e1ad4ddc2f4a5db3098730cb2e03b60a92ab925d1113730692e9c5dafd757aaacd378c071b8839cd530bd9b3fc668f6402a4b06a4e60946001d431cdadc965a3ec649763fe6080ecafbfd25ff447f1b039b1c3c36865b96596e220fff333a70320c867c4b6c4689b463954b42a8f0978e405f9592662202dd5cc1b08df085ba029f0fd3e9324d1ed8e8d32a9354d58f68285026a36f9c821de90e2da4d8053ff97857af06357dd5d64b1ec322c0d752ef7cb41ab63a0fed367e82de0a56d41b45e7af12cd6c9cefa93e9fce69e1e5e7476133b2d0b6a9bd45535b53880a1b1e3c25d66cbca79810d20a0d0f1ce75d3f75d540c5a08b97ee1f9a5656cfad35ea9e16e084a3ed0f56499359af8fe3bf7261445a3b26b2e9e369128bf1f2ba07c8b04314eb8007eccc98639fb9fa1c8e3659b31f966c2ad2d9ac87d620a72e524c66033e668a5f82ca3308062e163377321abe3cd0a91ecd18677ad461c807c67283e38ddd9fd4630ca56ba4677610467121f1a9340093d5bfd25b357042a4877837d15943d88030d6aa92b1219f5cf726a0fa479a1c3801a1fd595f3109c1ee7ba2ae8ff7bc7afecc9543f3cefb2929fd2e16a2f926c15317bf82286ff363e05cc6675dcee9e79223827efb06596cbac0b121d9bfed435c90c18d47be59731bf009d0046e85a372321bfee0d461ab1a9f0fa2efcbe3e7bf8ff81fd33472c9d0c94b7218130ff7b71a2f4312461885f522acae72611321cbdca75b9a6c7022a4a6f6174b44a0ef6b9e7cd154cc658c4c23191eb35a2272a159d05c8c4f0aa3e0d8b697c9e91c560b5cbfdfa4b44c4a08e069e928a27801f329a36f637d75d0e9c5609bbfae1eacf51cb638c5ba85e019fe7c9988ab568df2af8ed32967516133f2126a3a1664b413e3f351c3f71a3deb0b7c2da77cf7837134f7eceeb726a6b59b859184438e550cfed2fdd67471739d45ef466a1754cef44ff889fef156674f6dc17d862c61d3fd40de741b5aca00458035694dc797a3539e6f0c057c9d2d1168272b0ad099e1357e529c7936d7d18c68c8893a90fcf59efddce44913dd2f18299819450c4c33b93d7e4afafa1f56b9fe921512fd8c908f4ef9ba0b274ad535be43f9acc3e0c10bd8f4a8f6f51b581e1b1b4341c696e66682f974958b5e1dc23ca636f0f2db52d823b1e9a68183ee8a1f30e3be248e9f15e83e9c82b4ea73c20f58793387ccb68ac41fbf1941d5acd001a7cfd3a6ebecb901134e0a665091913ed6ca47f01400d9a6a3e5bde68475127c2f53cbad43976edcd336ebfbdcaa83be7e5104710ab41f52e6eae63bb0ed070d34dafaf78b4bdf6321ac9a76b92a76d35a4dc3210c193dac977500d617f20bf21a09429a965439f9756ef2b8bff48dd7eb294f74f7c39e40f86f4bde4f792f6d32caade50fd4e151e21bf50fc098c9ae1663aa3a018d77aff453cc732e6201ba32ff104abf40b00616e6f37a4baff663eee3f6b549e0b72b205e7408921515471b0233e6857971f046e284fa96554bb0442f8388e3feefd057ee579b2f64135bb2ed69e957e25ec9da8db5063fc8a61b81e3e1c824ad4b33640f526aa6be1f9d6a67ae30ed18cb8bd523a088023eb6b75bf5e7d51c65124306728270f5b5163685cc83e5a86f5b61bacde8766b97cbe6db1371466405cd211a4497232268aaac94af791760ab7ad7dde3538b87c7436beb4649b3043dffd9a4ae0be9aac0ab2c54a29aff3f90442209c1bd7f681b2070ef8f1991f9f95f27905bdbf69af3dc78d2fadf87395f3979a760d16c106376dd15289acfd8fb61e953e7c67b8a46b81e742cd9019650909fd1f0b02d184705ee618e61d7c47d2aa66835885c954077e752588ce81d4f5bcbcd9f018170a6db06e42aaa7e215f8f740158404e876b0384c57e9fff466b3583aa5be94bed7b2a037ee72889b3896bdc0f4e69f5a75998844331c1da2c728f85f3bf07c5e8b89ed6f426e30a428d88107d3d43086e6965fe13cc336d07eb1b003be500642ec9a8b148133ddd8dad26e40e19a534bfc65a77aaf4e0eee1fc2c40417aff80716778c9f9297ada5f26f0e1b6ce9d87b97871d4af25ece506e4219166c9a9d122b7944f71efb9eb2c7ccead8b971f93496c0b4d0990e338a7e0a6086e676ac826aedc692e99730d1d4adf6d659b1b4a55f6fee85ad8036ad44cb3e652d018b590563cb62d5870b5e461339f8dc284a8b5607cd6b0753d40fdbe091b45826c672883e676555011ba57588c0102de9cb5b9bdcf0eee5130dd411143e33c3dfdbaa82e0d130fa6852bcc63264d327e59ddf681453e29e4fb26097a7f304f7615e8acb94e1310c752b10e22c3d2aac9dee36c18571905b796b56d1e2102967ee2271915dcaf0bb964212339838e125b40ecafd8791a659b8106b795acc17be6d2784ebd2ffe46b38e751425d16e84b77622406fb3c56c58ed2f8fbfd90b8f8f6ca556d995d721c4b3ecb463cbbb57f089ebd933c3da75f3ba1e18c85646c0b6a4e3b1db82af0ea92895d2927b301ebe7b44571ad7b4640478ff5ded03d027bb928d5cfa5dd472bd4c2bc424f18b5fcc5d12e3b46aeb22456788686e7e19ff513bb323b605dc55dc40e632a670aa94197c4529b7278fe1b2645a5c1a8e01e74de0dd1f675c080e39613b95efc775fb6bf33c1fd957d2abfa05f1578a54ad05490bc2dfafce4c9c13ff672fd8c5e3c851b8751e0f9ee4a6727d3fb6ac8b319f409a541a24a1a973fb9e58acd21d7f977e4b1825ca4e513a85f1bf3ec318a4b381599ab66c5c18df923de12c690edb608b3e4730cea8392ebdd6a2d1db47acaf49ab52ce1c433cbe387e1755734d3709138a4d8f52af16562f86a5540f210a1f6c8f79c88d2b9273b9d9bd92c043427c1a4e880dfd7258fc7bf1f884c40ee79fa86853211b0598993f5581e5cb1f1446c41bca000247e5a7cdef0451c79c2f91e6bac5e542e4c56aa01d9b1453830aee2d9c49aaf24804ec3d20beae71c52fab1b449cf949740b8df96ecc15763460ee0915861edcc71f62d6029ceeed1952b879482b5e8559562b5db820a12ddc9fe427f50fe4647778c71e378a1c9aa57a665015370f978f005c0f56177ad657236fc860094c17477b776eab0da9b72180e184e14d5e1ac6ab1d8a323505267c4d2667be6e11eafa5def4b0544e91a3207e231a7f71f8bd060b09a220ee70485901ed71fd1f47f07dc61dded084d9ab4d31b2a2feeb72d35d7b7e32f2b4c82262f8e088dd454cdc82c161dc3ce8350f87a111b61ca8cd84984336aec98438f44aecaceb6fef64e514734cefd7a20ff42b63fed6cb1447812b266222680c1f5df5b8f3993934f36aeeef302024dc","isRememberEnabled":true,"rememberDurationInDays":0,"staticryptSaltUniqueVariableName":"e58622878c5b4107a5c053c29b821537"};
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
