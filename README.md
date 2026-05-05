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

        
        const staticryptConfig = {"staticryptEncryptedMsgUniqueVariableName":"19483612d169ed08198f0a5d131f7e81bbbdcc7c66d7ac45cf718b6faaad5b9a5fd527fbf107888aa5bb17ba3e8793e90ce9d95f4bfd965a0f8065c7b26064a6c03f4d668b87cf70038128199630cc1df66b490853b475e3cc1051821f9165b13aa2d9c61ce1ad2ead25d60e77b9d14da7e2d105dcfa472d49f0890de8e3b1f61100348a75f606ac7757c68b108b7e53a62cf3378de9bc8530145fa908e9a3cf31157a215afe5c946b7e0809862fc7920f365f90413013dea73e76868dfed220c5dab9d350cd499ddb9f5590ef0baa0ea8f5856c84d1eedba97ad80b1da89d1e2826b96ab8d083b87693be420f70f3d56ac7d23ddb425a3a1a1ed3267d5e98419a82f4ae4840c4988d0e3bcfc592a41245e88213ada62028b4623b0eb99d33cb6a337ab3a12918c0e27310445601be9d5d0dc12ac68c7be8d4f0c5ec5df0f0803e020dbca2db7feb84ed287c56d740db2990d6624d2ff9e89f0da3015e49bb3cb367398a0be40efbd2652400ef663cc764ef8b91a626934fae79e5e83be627a48af83e092708dd48b8f4391f97f9c229922e8b5e23ca88d61fb9c7c6faf99e248eefc0e3715cb10a8d7f5e3dc37ceb82594bfaefa43f8966587a13324796d91b1b17a5818f4555f43c2e05da434f3dbccc098fd064470fb7d794456661f52ab8028dfe05c65b1837bf3390ab9b784d7eb8779df2eb3480bcd6f56790a5ceb86750b3a03c312cf7c2f993018d32ca94857557e57e51b68f076263a6f1abd45066657ca5609c7301ff5d368d2b6c46e26711072e55397d1a3435a3c6a62816e79a5e796ae0af8ea90131cebd6a3b9525ac33a908da6ef8b8503dbdcf2e0ec9096670d6f8c5e243739ec68705139dd9bea24c5741ad5b8ce4dc6f6667cba8d34fd8c885235b97aeb06ac820f488b2a6eba85eb6d3b87001799d8b41b472726d8c1e5635b360b3d57ae27a1725041f0b2eff976e75f3cab6d36e2fb5d4909b068b96f32de03daae19c77bcbafb1639250227bb7087235528e9445f55fb8c6ea0f91952f4c6d31af0a7cce883ece8c6cb492712ad118fa1ff814b4cebea07bb6eb224c6b679fb72e8f82f704007b4be0f99bdd9276f171ecf5354045f9878ce7872f2ddfffbf35aaa6a790311c25e976630c0767967f36c096cc3349b7ea01273c778c749ca8c6474ce2d788e5809b37cf204312453f814abbba71e9ae604293ff934b1e6997c6f625395b315aa3694c31c4698788017aec5b3928389c2eac8d6ab87f92788508f8d6636bbfe095b4ab63f3aaee4a0a51682c6618092a6d904510e1962d51c3f80807f613ad16dac16a91151355c88c0e9f59ce46fec3170024365f2454a88823f00e5c88f47055d365a08108bc5810ead1c8d877405ffe4dbea103d864f84187a5c6a97427ff593317616ebf78fe8fcce53c6fc48c918b7b02bf34df7b6f39c0472d3e89cbe8bac96ae4d0ccdc68bb8088da4ab4226eade8605acd9c8aaf3440882c8de7fb830fa4e475479f50099f84c1ffe827c77d98d6ccb8bcc346a2bfbd5aafc13f2054d4c17545b766ff3f1ae914074a9b9e454136fa59c2e4a460cd84e9f9980cd1f4f7f95e9ce912aee01a4a9cd9649de51e463b75d1e653c04cec33486f5986edc35f88754ce72e13159d145d28f991f50d3bfb5956a4ccb2a4ab2ed5f797d7f3b79b741686e74066258243fba9535aedbacc11fbab7bf86593caa4d1526e3dcb0721c0da5fe28ac7f80cf900924d03a220424638b29598cd360ca175ebda07cbf5cdba29ee4d0076f8b63fdb526ca279c30b54f5d43c8f805bf851fdf3624a2e11b5e03aa621ef9485552af1bfba221ee1262ff0f0d73b5848b8a36474aba6d832eb1ae7f6c833764ad9cfef45a8e688e6d2f769a3098480e65a79416d28213357cfc837f2b199b985acdd6ef010e4097938086ced0ad721e05c0414e96f56188d9df6356cce778016c023a1264546f6e66266c6cf2032a482e4ccd64e8c0414511bc1565ba2e20b80a8b6dac39f9bbf1173efcdfb9d08a73b14cd7bff5e5949807df1b7e40ae0185716f51057b4ffb948d1ba82fda9531b214b0755e7ab7d2a0058e351c32f59b7505f4f32fd7f755fc687bf1a507fd60e338435831946ac0aa749c75614a341b081e0a4bc56ea368c47334162ac6fc5ca087c437d935a395a648d7acd9a571d0ab98d9260a82833f45b1ddfc94793caa3c0bc833e4b48c305d811864542a90b839dcd70c70e465ff60fef6f13d4569c2edd9134bda2eadde96b4527b15d96d13f96ff57314a89e43b8453cadb67ae21c4c94412e1eec8046029ff9512f58ade0990c2556649e6b2c8af632c8eb9dbf92a9210ef2925475a24eda31f810b24a9c18dd48e37bd03a89278ed30f9cc222072b36d676f467f6784e31591391bd22162ee211d01e158d994460162b8b7ac3223aaef83384b9e63d103a3b0179b0045c17e2dd23e304f42e069cef32796d63b65a53c793d97f45ece8ac7bf05ff35940a922e3970c63c14d54bc7e6ce88ce62d8b5ad12c7b39f222bac1f34c130ebc78817e89e805f316d5991231a4bbbfeca6ad7639dffd8338bce368f1dc5ddcc83829c1491b4a3678b463ad451bc22f1f778704deba1399c65afbe0da11d3aaddfb4c22b5277e52b094a95f1b4f6ffe673c04ba45302c339a7763ff863d39c2a00f2df826ae82d3e4caf75ec65469054c4367d128126eca64eaac8920f4a550ced29fb583ff90671cd819677fd38eba06814e22f05c3afabfa21aabfdf556c43067bd307d91fc26992ff2e8fe0226b6978c88cfba73546cceb6be0a0eec514b3f02e5163ca5f26d5f06d4cf4f58a9903bb6e0ffad651504dd974a1acbd4956fc90a62b57a3a595fcffc55964538c201463049eb0f409f28c1a6565541bbe64f03f638a30bb39e79d6a2520f443245c1551ed1da6a0ab9471359dcca203abddb7ef3e2151eaabe7b9a9ec7e3ee5257c9e60bd3e2568d847c6e52832750280c892dea5f2f8a441648b02a3937fcd7e6cdf2be0e4f2612e73514d0a4aff1966a5ca50ca4b2671051d30555ed335f9221843e36dae745bccd782268981bc4d20b97205473392908701573cef8692c35446b21ee758dba2c38c81e22046cb8620b2b33c7edc6bd17ec988e0d3bcaea47f8a24826ba2061f3ce2b404760a8a50348b74701ee32632bd24e1a9575a253d46777be58b99acd80a3e42019124aac4033c3f35266237d11e9ba427e66939b8b4994cbf2d7af8225a361deb610e65ecb4b39a94f3cb04cd27ae62ff988cd102406bf4d8569ce176165f45f37908d27c24a7a9213ce2c295c08ef33fc3616787c54329b3e2e73439bfad93983e594e7566ac40f40a8e689b9325373db42caad1f8161c114b573de2b91971b06d5ed3d49959a03ca4ad2822764e41392bf60df2f06e1c66cc79899c6bf514b98ff4175c500e7e6258bce791ba3d7892992a6248dd78741eda1aea2cb43402a70856ce1bbfd88d3f52866f0eb3d2f2e6bbfe660ce9d674ac48c61d7aef2589c98977456f0941887e005e391db6f5e03940322713255ad078ee2d05879e960c0723741c661c1e9c208ce73c4b86563cdc36491417e863ba07c676256d6a5da62d3b48c2726bf33308a2f7f23424e2cc7803a2a71bb15a22c1cb1ac016024a6fba7f1eeb0303d396384d7f0dd84a5e04ace4147da8829239800f0d3c2e255b5ee1f8494528f78c4bcbbc93b284323b021e055df519b2a36f76f731933a115c8dcd1257ff63b5a9bf31c223e4ffa80dc0f1cac68d299922ff2c0f945acec5538046b9b356639163d92bfecf8630d7bcfc14fb06f9ab807b75fef0927db56d1adea13ad5acf44cc2c8bff2b374399d06e1058dd9d7b18c7ac770a4c70cb5463c0c2fe7af901571757000b98c3a13e5aeedc79f89a898456e0ec549bf90b6ce52f9c273331790745612a0d0e76b99524168708d94a42e95dbe6f29221b8ffc86fd410806fce33a04cb9bbf4cc752b6acd50a28b99914c534b82b8fae7765d5c4477a3d8ebb1ada68a40cadece1452e32165a15a02c0508a4976befc9416bf91b328cef136c9586505630d41effa368cad8d4335ee26ba107f033cc0dacb2ab3046b58e176d57a39faac93c24338ddc846173155c7f7498063a86ed89d71531aa466f7ba917bdb3ddc8b37bcb7b01bc35e2e369f0d9248a8c262e17ce5917c2bda75147839679957eb13056c9af8c881010f93651d6b368b503b3d6ab007d3ecb70642f4ca73ab289a27321186dfb3f0a95a1466ed09f22789fd24894b7ba1b7a306bbc2cd68211f1c4466e5f552ed491aeb7504bddf17fe7b76efafae95f53d5d5445533a4fa12bf51bf1d57e683877bb2ba8bb11fe7071d7af565d1f4d4c79ed138b2bcb011132dfe9d0a92f8bb4cd7b51e0c263a3242e8083dab65dfa80954f47465c174747a4ae16826bee938143decc71f53a457410a0db7b4568b391c97cfa2e3ff14b40f217fe81094fb9b39d129586b79fcf8c843108a01a4e5ce896d4a7da1d5ba9aa49dea4488f4f6a2707feaafdeedd5907fd4eff1e257468e2c2da87f2894e9b184367a5b704c0ed55067cc4065c9094a23880f95df96d1c5433ad57f64fc06545701a1ae329448a33c41b9eb6f46ac5a975eb535ac5bb55f948278225f4bc38bec4ea5eca60e237ec4464a36069437cd0bf4dfca82a76f32eb539edab1577e47d1bb6c68519a9fdc981feaecbb5da785697d4c48e21cb4177b445ab33a28ae3adfe8048a225e0e0062869b4058ae1f0b202d84bfacbb2edc486d93dfaed9e1ae0105f26a71f633d10caa8723872dd341e741f831eedb9acbcc4ac4d2b39471b4acd62dbb5c51c9a14244d8c03fed96182f8ff8c5efa8466d440470a84dc2617025cc5390db7c52a41a2f8791f859f79f172b530659f428d22ba731530078bf3ffbbefa9ab3285940426dd9dd7ec0c201fd46a86dfbdaa2c80cef8f319337d594e9099f979fc7c0a6626b673ac52b135ce5aa0fa8bfeb35004712603b4867b16720510b0623d54262ae49db971ea730b4e919a60b38d3727538f07518b3281e0c0acf0187ff7b197d18d31a937e1d3ca497fe6b3b3a757ed5c3ac48734f7a3f4d1cbb26bda8c63fb38fc2c9cecb711eaa525187a474f1f537edab413c3a5405687b8527678464cf43e022c7b986ff5f798560c12cec51c7d143990b7f15d9676bfa024fbf28fffdbfd4cfc67a32288389f220db585bb4817d05448dc5c4fa24527fa52fe8798ed55366d8c2af1c818009a4770bc47bd9fd8581834a752de7e7a0e8774149708f9497e8392df4692ffdc94d3724779a52cb68d5aa47afcc49f719262dee194feab19ec0ad1215df6ac150bae9fa704a925f262c6750b95b13098f01c234a5335b6df4b47b76e625622ec8171ac36489499f2cd22f034b817296ffc18011d921ddb4f46ef8aebadc93202b86d797dd6ba2f9d574c507f913c28bdf5229bc020fc579f8a766694b4d23a55bc2875d62f9dde617230f4259fabb70f0e0a7ae7b2e299cc20b5d28c3d174f89168d575e13c2be2003f200eded45dd2bc9f98ed973ccb42e04c572878eacdd8c09c1da7e62e8dfdc8ad4a26e1f956b19be928d4e0141f69c0ea1b261d96bf6ed72f2c1c0715fdaf9327707682ab806452873e5ffefafb0359d10d3413fdde862f90ef874ca7cf4eca071bd562eacd85482b8353501475199c172116dfcc95575e974b20d6b2634121684b3ca2aeb61b9d5b4cb79205c72ab8da82dd89d4ec0609f1e89c2e6629b6a7352fb1ba74cbb48f33b88867213f89ceb66457cb5f35ca2e8c60986c380ca6f1ba59efa850f294a0428822ea41c46c0ea4e362302e251da7a8dc4a99ef06d2834290aad9e3a9bc2905014a027b5d943f6965e48b7720d1561efdc92b6de7e53b30871efdd2f8a602a29024452e41a3d318fb40fca2c6db4dc29b1b43a1775fb0bb440797cc800b838bd9f827b86842e9832a422d1531aff1163715a92b882cbaecb9a00e6b168624546da0e0132ee4045c34887f2f60b700906c08a205b629cc8b13ff20d70b33a50219d64911533b95f91f0f174f0462f7f9f59d1620c5db92c38e92c2059961e8d6df5c70335b236459ba11d8c71ead6a5f726f64484920afe0429db866e75d1b8e55a87d4e9efb457fb7ef21de4104d1ee4c5505baf170e9a50c7f092536c4a6a069510a395433d87fe754fd509759ca78a26898e8e4b387aa2f965dce1b31727c7263f35348864a7109442552dbff43a903daab757443e99e3cdaf39d2ceebd650c183ee4c006793fcfe3e9dab1ca8ee7d5446efd48157dd5512043b9dfe56e674331e85bcca640a581f31db0a57562537480b10b0bc7815f47b1d7d7870522f9a7732ec7d4e936f755740723584568d833ec504b92078d286cfb50d258b5990e09d6f574e4f2cf101e9961bb709ff5c61b4fd3871269bdf24974332e2e75cf467c4164e286d858bfc6f6a3d919f17638e70c926f26e2f2ed49f4df25ccb3a0113e95d7d6e20570d616c03fec9046ff7c17028dfe4b9ce4f867e7ee449b2bec3b6e2da822857d0fca64479b2263e1b78f878b0e02d313d1138ad19e20c3ae54462690ed8efbcf033d87ed3c7519863883f0924e7e52deef8537b227a86c04ed5217b1e30ee3059503605292d9a26a6d2e4fd45bf68696d44468e8d0b9ed63e3b30e54fd4fdf1ec51c657f4998c224bed0de9e12b830c2c2c6f2a3feed210725005ef46a91b672541a54b2d7fd7ac014f1714132aa4ca145a1d37d2e056cb4cdb5c8e09652863eea92c371dd3c05ef71b494e99bb4ebd0e67ab02a58012b377afd22dae8e70f8373aec2e84e5544ee51dd9b0daa86e48253abcb6f0c1ff90f10521356650dfd8d46874446e027c2d6d07e358db0ff8c2ff4d8d64dc8aba9ab2b85a1fa4a5edd63635e9de56881f597d9f6f797561b1850ecfe09de309f847c98caa23bb0003b40c4256dcab91f0ce07dd156bf6a35b707072c59282ce574cb46f432bcadeda334e8965a7a5fba85c9fd89702157019a36c824dfb8d83d8c45641859cdb0afe649b3faafd1eefb6a1fdb175bc46787e56c959c6fc2f3416f7a8330486461f5dd895b20385191f35219321af2a183aa551f782bb76fa1469abb4db502d54ff31b97f71bf737506f92e84d2d7fba8f54fd825c60af39a1846fadb628fda454f413902a1b7286fb45e358cdcb5aa21f44791511cc6580c24800595e709c0d59b4549f2934055ce860b7e2e3eaa57cd623db22e020c56d5f29fc5f1d85600320ab568ef6b0e3017b8228bf1060ec2a57495fb9a7d5266fd12570581d7c83457147976ee345963f2835591f5bc5e25a53c2ae7f34a04b9c91c9c7f66cdd7aa4f19584b71a10fe93f853ded4655918edea969e40d69a6ed017b94ac87ada532b372b075b226d2217582285d6d162e51a75a061361f7400b5f841d674a230b41792940faa94f8091b5a1290876a501cc64769d9a791be3bc2c22b44f73678677b05c967113f7334777d30d7ba3ad4ef34e7da0a1509c5eb4a5a96cb0cb70773b1e9277f48a20e1640ee0a1e00352892bfbf95edcbfe3bb4dccea78d7f3f7f026e44937db64e4a6205cfedb064d865add5e9dd6e0d655010ccfebd40d55035c8ff6dc87c2cf9f2fa1cd8640756758d5ba36652c071178167a09e98cb8257c37f989a80d225e79a1611542459365d526c0192996d038ec18b8d98eaae161b44fe89c77ef5743fbdc30837e9c25f92c8e48faa91da743489721cca13b33536e66bed72116335d80e3176f79cb1de3a88089b39481ca7fe78415b3be7a9dc9b69babe210bd658841383451444ccabab8a545fa28f566a04876ffb8e7676e4b207a8cf6b16753c660b47a3c139e6b8d0edcbd7b143e9a2042e853e03f34696452bc5ee684b4516780e7878fd256ffbe86b31d21bfd07a2068c6c98eb8edf6ab1891ec47da3e005449e6e8c008a0ce792a3c1fe7fe7430dca5616044acdcb9dc4ad1ea68bb5d1d0b1d25da47d0851cfd3d5fe46705a79c05e8e102cbd0991a91eb54668b579dcf3b1065b216a7737a0d4ac08954bbedb6e8d8ee88dec821b2acf29ac4fcb98a3562f506cc36f15b009bedf2e968e7705e43d8d1b67311f5243820152ef9f53fd6df4831197de004f4834560df3c651c485d3771af2170b380b36583e1f87ef33c002b584be3edfeae5556b0d0d70143306a2899f40c9f34c2654f4a23dd1e2bfe142594a74ee8fdb246b28e63e929aeeab7d16c1b7190d1451e46ae150926f8777e67d3ec905153f61ab5ed51ba70f93793fe709d6348b2fdf56b3a9746a47954462e1888b88249974480c8bf22489353cd3a05601b8a18cee55242679b0ff056d4f31a17236a78e900749ec720e49ed644fdee39648631c1dbe4d086130f1429978b8579830fa651e88262e39e0a1c760cb949d0e9b4c85d910a79ddb3639b8d3bae9c59bba1c5e1e7af41a13f15ec184d6032b3372446fa42fb457707dc4e775edaa9dbb9f45a2478924da727f031db8ac794bced5d0545b795c550647de70b0b7bcdc380d5a61fa7cc8b86cc8d59108df144ed2fa0b7f583a354b5e47e1486b27ad89e1cff4f05de3674be158df52e3c07c21cb497525e99bf5a55ca7e0f2b6b75f55b3b4df4c9f7bb5102c67fb6b9b99a91c34cceb798919da112af1637c4d39e68f1e4baffbb950700534f0691702d4d3cff9a807c8f6aaa58233c64f169c27e6a5b04e395bfa2ceb63e5b84ae2d8b4c162a098a218f5e762c0939b9cdeb612150bbfc181c4ac6c9fc738d1ee815e72df80ea9bdaa27f9f9c220e7e357386bc770928377bed161f36a3abbea36a2ef97434106a208426cdc6169d0226db1e8e743b1071a37f718b35fc4f3a8ebe28b9549fa3c7cbf945ef15a2d900ac3053dd1c2bccc55945287478e158e8e1a9bd6fe8801c22f5a95e2c0e2d6caa3770d0bfd5b44c205b166ab5c0f35ec279aa29f1a1a666b590bc4590743c31f5f4343c73285a51cacd4dd0f56daa7c50740f84e8e3eeb7e34d88ab96ee9ac6172e6186b96a94769ff31606fb221d034203ecbb8e3e0d97bd2948a22b67f5e60977c0001e2f5230cfba629c75647ce8c7c8e0b772f85b93abf62d1325dc9c23b609919d1e2e63e99fc3906eb907988bf343bab83a4ce45b7755d58342de58683009ca46205f664913ec751351e82bd64c7f0bfa83e838c80bb97f5a6b53022f97a733c306673e1f865339e649d000c7e65982b79e65daff4105cc1c8e47bc946399e50e34b10834cf1e9d84ffc55429bd3b6b3a11b5439d0c585248fc2e6b8b4f85cab1cc4805af0866d1155c7200635b12512dc8409939917303db60e9b4c52f0de38e9e9d43f7123b95f0a75dfa250d3371ce413bfc6a30180a883e59b1e9a8c47859bb440df1eceb7e0126a369e4e481fafe755fa59e56d200ef96be60ac6b7178b542804dde832efaa5487e8f90d4306539d224ed2b94eb8d31cb7abc37b14ccbf7c1adc66b83d7f6d77ebdeafd774fc66de94a7daf91baab20874d21057218aaddbb87217e495a9c94eef0254c8724dbca36a3d7cd6c87fd61bac925c4b9d6971b8c34522008ee201b178188956b71ddcd07660629d0912b57cf2ed39576ee32926297d64c2fefba2d365904f25e73417907efc025d2fc643b329a4e266188ffbc092a184231012df74da783efb772fb15baade8fd73b90029e730063bdf678222c97a6e4aa7ae8fe15e1d9647f4aba58015b295f514367629e26ced1a5bffdad7346c5cedd32f680201263f31bab7056eb9be9934f21257746fe0f5ee5f70e3a322be5481e6f32a793d04b31f6222c3b35b3c06104551bc49af6c7857f2796a644eca078e562b3b6d9e8105624a59b77de8206ccba68c63f42c5e2bcf568fccc489398ae330ee89bab29581497fdd674742dd9d5818cae4c8895288ccff0fa628e662ae4b2764f6ebc1c70e934aa4ce4d806e079e77b981f6639400127c430c3669b0cca8c862902fdabb81568677be31f7f43a6df50ec8cce6d7f1de427a984b6909fd920e0cf59b4a142d88f65dd0bbdf24ebfeabaa601b14a686457a68c08beeb4357ae6446037a091274a6485dcbfe3c54588a9d612153bd9593391af90fde20e686728dae61f16815ab34eb265c829a37444b120dc05de9449eb951196508344064dc4749cd444df6c3c3b434caafae586e8078cdd66c7dba89fa3c14e6bfa0d17d874242a4fd817fe13d3b0c1d0e8db1aa001d3fbffa19432d5f9005f0c59522422069892de9b4fc2cc9b8e8225a0d2e182e66e6f32fc0fa1d4b1b5c8346a67b5f0d507201b25a3f91c7d2c4f92a02b00c65de9371685c994d200b3a1c344264bc281b724329c65e11a7e8389c1821e1faedf4379549ebbd992e6ad446c800905f8bcbbfe327cc54a230a554438064f8bba7c29da0150dadb78f9ce9da4ca84c68282c86897101c8b8b173760fa00e4deb8490076bdd3488b82829f0b0013c2630c86dbdef8ce6c0102690df433fed72940d3a447fae260aa491034be1ce962ddf54ca83b40da559521e82e1693546fff5f5c27c744234ee5552a065b7c74a085cf008dbff570d3f6b8f7c6f17ea6e27dcae635b592dc14996e1d3666c333cf0d75cf7c40259fcf2c2960742583d61d8796a4694f0e3d060ced561ef5cc7f051d4a93df31a2ca7943e5e0620d29c90f23871368915a697de41754d0c24ce9e81ed0c176d4f29eba642e46e8f28f9d15518f83f5c093d8cef846efd740032399a4b4ac1a5fabc1e36a949a7910be89d082c27cb66aaf2f7ba2b3fd61c3752985a8b025a1a44ef2e850ef0a371a78deb5dc2e5e5dfc638f4dc492144fe940681f4fc58cff4b41059dc3f7f6a05542acf52ff030087e98c86a9ec26cac5e81f7feeef59982aa43cc6d51f3e8679c4b1ac15aca75d016aa3d1632cb545c6cea0dc397cbc2e94758a0c4f36e87f6e4ea45c259fb7f390dc1cb8c2287db7ac7fce35ab07a3e94191a1df20267c8b9f3d19f921d8d8acdf64e7534f3ddab325145403818667b057669d161440eb189a3dbb1ad770f02a6462a017e546047336f5d8b7ac2a170518f8ebfaf1f957b867544fc0dc6580e2c57bb5ff06153a817c761294373b454fa59a65f576890c9f7800538501f71680aa1ce3e8b3f9f0ee5139a7a8083d193964388a45835fd78739cd27d5317ec6c470fd54a6a99017aef43b92238e4858bbff638d51b3dfb963ea77ff12b1de44af4f6f69694afe84ab9a58b30a46aab038917e62cc629895d46002678f1becb7417b3bf7142ad3c93553bec94278eba2e98e74d5c62b0f42202be366682ff5be4815d1a50217e0d7933ff353b0027bc7374dc7b9253bec9fc290e1312080802377d07fcb0c8c1cf3f4d3441b1ffb6c6c1ec0ad36cbc3334afce91d6c3d2c3c9b1a5d66ba3d80886b9f78bd97aac70d656b47eded92fe1746d595585ecd5da5e6a0c6b848ae9e808be9e1dc793731fe3f7e78566b467b8fb10431867346162e1f73c4d24fb6f940c9773085aa2c190fefe7abaa6880aed42f719ccea18b1d75ea517d8111c306b3cc11443b088d65d77b25abcb5bf78dede6a67c37f5dd4d0f7a2a2f7187888161c920cbb7ea5219769ec84477612783af2c2a10b97929f39b6f189e6c628b488a631fcbf13aa7698a9c0606984c4445a1364eca18233682cf0c4805f2aba9ac59a3a63f0cf50b11f3c546d7c6be44efa154e689952236de3af791c505d39d997cc478e4558bdec77c9cadd95ef854578ce8e6c263f8dd87c0ded86c3451b40139d4cb87582e148e36f2905886e8e845ba164be1cb317b0322d936605043268058d7f71022efa2efc40aa453ffecdb2c943d760a50e172493288008aef54a0800f3b6abd18caef36210d0d962cce8ccb7db0b308ef92051de045fd3ef477620d1f0a237626a2726b1af1905594f06bb8a650414a7fe27976443afa5eeea73c410f05f5b6f0d3cffe309d8be9c0cb72c4fad74bb47d430859f13df7fffe78ceefce76326f49dcd91c89a62871caf06da9c888488e046f8277de9d3033532b0874dd0fac2c8322a0e3c230d4866192d827411f46601c6a4e5f89c759e6977d7f862b8b4957f78618acb900da76c48b5505b25bf6df3074e1e8da095bb46f720428ed99490ec1c0b2fb2fed5ae130fcc39522e0f44a50e980b8e8e5a42b5ab6358dc49ad6c1ac4f0d2ed103b799751779f1c9312b79e6ca32744953e2f970d4f582d8b0aa60664b3b8a49faef63082877596bc31797fbcc27644ee0b167c699d8de54f788d4799c70d92afcbd0627e41eb552ebdf2fea6cecc07c1561b12f1903778019145f09ce974df6b20c3da17bef43cbefd23290d9d100d309271780b2e44f390526bd3f995cef098094f430f4c2728bc3c50f8981305ac8d4bb81f7d75f326954e288932f3bbb8fd04ac5bba50a3381686cd89d96129b8a68b418b5760b0f036706653b1dacc9674d53d606b166533ddce03af523f83801ec6eba01c1f1bd98158bbe0e7fb7ed0c796d8778c2a78a7a75dcb5bb73413aacfeefeb0829f87813ba10be8ddf11dcfc5c08cf238dd570bae9ac91a7e465d55045f0ae6562bc3a11284ad651476c849d1257a790e49c632a330797931020ab3cb405ab9d156355ca18b90cb68ea7dddc51103b332d4704175d36901f8ef4a9bfe56805ed0eb61c486a6296e1448566fd2058a867dffca870d8ee48237fc9d7c99a9e0d2d4652841a5a5b2fdc1653ae46e95e1ade25d15dc18804c4f26c82ce8a715ce56be5bd807264166e15bada86084d6c3623325fc590914cc4ae0d11883a21461f39b1c0cf45ba0cd91d6d777fbdaf1726a3202e692e4bdc0148786d641a4baa5e7e7e5a6867df63b2a582f1ef800c7c525589a1772233872760ae777133adfe377d1b548e69928e268c64b49ac3568b414023c67314234a1cacd264f46c5a3cb207a47c6fafe2e49a7bb3eab9d79a1f6ae963ced16e9d14ff04f7862180cb8c2fa2b4d6179b013bbd32642b3c8f9dd6701ad8150dbb3737642e65b374dd994a560fcbcb8b214a61cea40224ef08ee12227a18461e08c726f5e0b319680b60ace7ca3c088bb5734b15cc8ebda0fbcf16ab8dff6f2f831e0f43be9f6cb87d12ee84cff863c146696265e60e3d822556a4dd565ad21f67ddf113ec45b652c22c883b7e71ebcfdf86b51e63055b97b89e6863eee4739d1cc5177283f40eff5c09c01094e3cc8f3dfef456a3cbfffb8958e345332fb5f54a67d5df4de667823f58ccd173f8df4240aad7a949155290f32af2835d2ac84acf984abcecf3e4e2435badd8f96135413e2942f2d9112ab6652f2a4f2561a346b44a59e079e5c8982da4971d801e89962a61f00ccfd34d69c71f01a58eced66d91d5f93c21832cc7024ca276b3186e102d0437aee286b94e1588016715e8801229a12fa30f54686a3e3b13411bc01b6b518c5f17b3c201e7e1caec349b1b73ad63b9cf4d5fc223b2f866065aa2b7a9e099c1befc1b2dd12d925837892107789f36750bdc3f58e62ea04b820d2dd06eaa31630b3e19433ce554eb6476a26aa42d6cb0575047a76fd7d374ff4715ebdca35c0b0776baf26618a0204a1579e0d6b1d6683a3694a333089f71290893d1a8abb712393bb035e9196bad25a78f960cd4883b6deb9bb11452a58cdb502e0ad8d37d45304ef8fc7f62bfd29ee5be14b6d7e9c60f5378540dc31b68628f3f058e5ccc6b4b94ea26ba6a16595bc033547bf03905f21cda88632d6b17c920369c0757325f9e0242d064539091d32fd317633f63c1572cec8915cd285a17ebe40ace0f7a9f2bf7563d11a575d440d2c050c3781aa429d2b22db8bf7d39d55f6d416c60849f99ef865751b4bcc7b6978bc1fc032153fe031d1445a3f11fa4e55a9597a54945532aad90efdfe9cefe893d8a112e730c2bb323b264a7322a533026333b636a4e221fdce80928cf41b2370ac5420f143246e6e946d167c1d19a19d53a7a74f5568e44daf718fbecb8eb2c507bb98066aa7bd47a46a98985b88c58cce72e13a76e81fbc3adf808f7010d3e42d2208ba322072e3555328528cc18e6aeeee41d198bd7607ee348e32fdf923ba641be8f2e250ff34303895af08eaef0663d8eed20f4e2e39f62f2b0be0e37652ef7e9eb6735a2bd8be1fc3fc45123ecb848a75e5bc89ff254bf2bde7b8de3a452bdcf129e42c993991d597931205e3315816ad41e5609b58bcdc3603c918fdd26c41d8ab2879d85307c169bbfae834f836317a4ec81688a6eb5888cad7ffdd2b84c0fa3cc4306d774d7bad8e9a1df8d104dabd3cc2f80a0169b9dc6a04efd9e5dc246dbcd7a705e3e5ebf3661bcfeee058671fe5be2b1c3fd18582cd63a3600710d4b69558f95ad05dfda8402596e3753bc2c6a42c283f12b974992130dbdbd3e06e34cb7f7aed0340e3bbafad2cef8d6b72c30d34ea37fcdbf3ef9b65f71cef2546102cd4e75b02a9bdcdc38e0e15dd18f9ea498fe8531c94745d74cf978a2a2418f48b4aa8f7a96cf617704c57224c55904f798ea9da6680ce17d8e20a09d6b8ae704a92ab5c533365eb98a82078c2d75709b4af18aa32b7157fa1fa848be5b63cb50ab116902485e6a79af26ec4a920026f377e8ad1f9219d6316b8923e3455bc51fff822492333f3bbb865ef6fd4b122c798120e2607db0397aac2022ef1b5a9b3592dc6f4b81d2ef3692ce969bc4bd85a259b421c31064947949ab81826c41e36689d18ea97f37fa7cb309a2bd7f853f486f0f0a42cb8fb8cd504d1190ccc95151b221fbdde5f5c7b5ba4e22a9bd0f1f9d63ae7013a1be03fc4e74e6c0a31c54b6581482356352c62670a89ca972b7b161e19bd3b0119b16309de33581173f87abc7467fa6163a7eb5cec6e99de2e1f2d80c0430d1e6b0ef511a0d43cfb7a53854fd3fc991da56e47727e7406273293db1f3ed7e21ef7bb071865944b9eea1c6621aee613c16a3b2e94504002950ae491977084932b3a08f3bbe956e59f2359a4826cfa27cf59d61da9a144bd65892844fdff7a3116232783489a0b5ee9e7c413d294d34ba440f3df91a8d3ceba1ccb78e5fd29b96ea7eb8274ee892f9dbfab8197231f8c01bda79e525765d2894302b1fccff957401f6a20659467a77f39a50f0ad73519123804f41623d7ff3f288e7bee58424b6a2cce847d03b86da07bcf8b068c7ba26a4718ccd6ad59370803df12f9844696888ec2e154b64366fff1019a8f09e9a4670a18cd23010474bd054f2654e48dc88e07500f19d8016f4873b6cec1d9013310f00d97349424cb717f717ff460b9b5bca6b3ab09fd658990b50380682c90fdf6de01c45eda41af5f7e5594dcacd9eaeab3ca269e377c36a997b30a4d0710977e5a05f909599d5b447526752b8671884aae72d887b9ba81e190dd892a45393e080dece24d39f071db543ac0e51c5083519159f5c9a71cf993a896d6b8723c26d0ce9fbbf1b9fb47c54ffa395e7b44b7dd47d1563502d7b7af6e37332be7f88ae301e5ed381f186c70ac03affbe3d814836c5d6f185262a25439fa12b3b61b3ce3e02b3efc784dcd334b78c05a3df4af3375801bc1124fcfeecf6dfe9172b868d2bc870ad03d8c7be0fa75eb84a3c1a74889ff8d6c79e627e50658f19499d2d936a4aec2d572a692bca7ca8502bcd281808f510c0a92dbec8bf6bf8d96544a587b76ef6896a6f343bcfdc2af1cce856e7363b94578a07fdeda12c4dadb768617ec68be46952682e3944e2445233f8f4a87ec0fd9fe0a617c332f6727fc164dd7088dea24f708be0b6e03194c51c34d1192d8948857aea3ef7a8d603d7961354acc76e76b32b673a0b103e867befc1106838c7ddccbc695a878895852785e66328658838e9c8a9913c55dd1aac63fa055592df69280989dae80061dc091b35b2d5daabe3fa054a3d80941d4ce7f02a3e99124008b2dc3f4ad3180c435b6cee88f3013b37c0cc7b4002f0d9f9870895688424f3eb74f6fc940cc07e898a6d306361ef4efce777643310e2d0a066cfb2fed40cc67c5d44bbefb4a5e6217e277678f62c7b46f5ac3561e1df7e1ff784a3bb546173ec65d906e8f8d35fc1aeaf9d02628acb9705db63e3be28e9ed8adb4993eaafced03041c6406e281f7797c6d1eedb153b49667350f3834c50d2884fbe8d6c5f0aa614bbb98957a99255a0bb9a575ffefa2bb0b2267038eab9dbb0cef0bb47bb02fb771e7ccb60dbdff0f6ca71bc903418810428d10f7f6f3cae2a9eae1efccc09b2cda73df3587afd13b41ea34673d0a0270a2d224965cf68de7fa8dc84077fb1d37f5378eb5fb0a68f41fead8a184654ea039329dd55a4870280481f4e8b8b063e30f1463c9ccfab1d274180e06ee202391db5ee669a525073071cdeaa536d935b679ab6afbc28e77ce2d1344a18400ce014da20a8464671e0a8a53b9b6dec29cfcce770a0b81fefce68d210006503e808b523911053a6189d85d291125822e8f81a660a09cb9d174c6ddfcda74cd8d30d5f9b873547f600794a17f9555a8960c151c9b95eb454220f8b929781c955a546fc3c72fb7d81146b78002402423337b13349bd831254749f735afa31913ea8f5a427f52e2257e13aef9c6c862e11b52a9dab6cb625678434391f8accf5f2c6c91da91117b6926190d3c65f7a647748a87373dc8a68d6dff0560699622572fe73ba093be1a8874bccf8f49f436e202f27cc188e4e583ec51e53cf9e2ae496dab60a7f33d26c06eafaf803091f641de8171936b3343ca230adf441b53963350a2d7bff9c0cb1741c0ebcefbbab69c4e1520c9bd363a7f8d51e64e7075171e4d259dd8f21763cdb40b520ab81642c6d0bcc2156720649c3f5c391b3b97048197570eac0d7da25d6337cadddb3127599e3559deb7b0ac55f2f3c99e2dff763ba9617b7cb3a0bd04f49f723ae0f795d81a46bf24e386a779710acfe53521830191f12468e6c6339ade92ee227c87514b7aadbaca68df87d70a5e14cea675767196457fb05a35b191828a1c6918871c1a800e5c2fba74be44f80bc7521ac89e8a56217a17f0710d3949fd0969ba7ecf8ba5fdd984730ddf355a3f07480a8d619c50ad762d022986c56d1f1d40808c57db7abcedbb3831684fe2c8f495364d59e81456c5e3618562208f8bf7ace7445225c9e75769c403fe8124892697acc98a31cc3bb15b374b7a707bc5ed6a27f2c5856ae065154b1349b81ee9b8b58b70fa519f84e9ca5e53b1e44c81d08f3ecae82fa5901a77306bf9cba260d649e534af52aca29c375c64b435fd2590a8ec572153116009e667679ea84c6527d6385bdbdb4e006f9a30a4bbde94d159f560f58099f5bcaf5a32e35b055880ea7a390b3ad5894b19bfc87cde1dc1c1ae973dec3e0cd8212c177b925b7098798f6b6706e73b5e2cecfa4f91b049a0598001c28856bc8c1071435e0f7b0b29867a0f1333b1de59b38df1646042ce5e42fb6586aab9b9ee28b87a53f7df74d7d4c6d1fa8b37f7533f76afef3a44774e736a9c1bb1a154e0a19f22a37617aa1808f40a3f7a64af9369ab7183581ea3198d0770ae7b25f37ab3038b32c043ce8ad512c9ed768999b1e4bc3102795ffba1b3621c13b0112a7f0c92fa6117082dd11525302bee5efdcd4265db5fb9f43c43ddb44ecfb295ef9fe5a616c27cf501ad035970883f461b78645ab9046c18917139fcdcf09d217eec18c8b3f95086df3a28d66c526f10eccd5d0c4da22e341a9ce7cfb3414d69117b4ecbc3a13a761ed60db41ce944c69d4ccd3a4274a54048105833e33dfff59dcad128857fda986a0e6cbfbd1f9fc7a31312d3ba771cbd5fdbff32b8109c038cd2f350aec4eb3cceee47f87ad455392fef36678f793ceb7e649ded7275b2eb0225dbe988be908b3ee89fdec97a5210cafceca187c6580b134cbd68d7be67bb2952ac576ffbc82ffb70627868a559506bf38eb196e08b512583b7629650bcdef12f072a13cb73254e162d1ff769eb7093a012e86a75abedd89d3f3aceff4f503e5fa00bf1326c699728cffa36657dd39b0d0fa72a38dbe61d2ba1c5e56a74b8d4717bb48e3e0057ec6ced9b0e90588a9c78c53bfd5ab21511f3bd81bb660778dd2f1fa73d0f3d26b85a7c2b0505af9442bfc4482ca02fc11c5c9b2514fcf67245b9304d62a052bd6bd7280098f83b996d613d189e45390c7e88af96fecd48b36471285e26da0781259e2595654534d8395669dbf552f60173aa2099b41ef6f61b9ab434b91b442450cd8772c6bf9386c1f8a47491d494fc2edc482307fecd779d37cbd145475c4dbdbdbea366789014989d20e2e911acc3758333d2475e8b5eb1363583cf29234704212d5865c6dc2782242f3d69e278463ccd14813ab57004074fb45fb2d94b59fc8126f9c85644e9707b63005ec2ea6dc9d796275610db224bb56eb26c4cad065ccfcffb5fc0032058ac633820fa6c0765d4177decb7cfba87ccd98ebb9ab271dd5a53a522d7987527c1e14553b788e320ac6d46230f4a5a4e84d750ed21009248ad58ad716241437f13fd9c0652fc553cde457ad33dadd619a360ad29a0e529565b02451eb59e4c7a7f7087b2fa54412808d8ecf7387fc20fe446f970e2cd5185c04743950bbf1703f02842aad75c0ff59371f738943abc7a1c9aa822e1664dcb29dffd4c18c44e0a0db537db59eb90a73bc38a4e43a304253be99aef5fbe6e0324087500692ccf0ff5825eb981f8e0ee8421a8b22f49b131a669a774a36fc6e97317324f71fe2ce6993a46465441b9bd462272648ae72989d2744f652347ede0142ae92a545d740dfb1bc4840300ea0ad66be09699ed693e86f020c1e92a16d566c2de6b17bc0d3c96d48e1e23f98cdc9de5d9a0850e986a875dc312b26dd2bfde2b07a748a5a2fdc0db6e9ba9fed9e19b0e755975f8c83493c09dcf1a2fdbd12c093cf236a9fde8e9e1f5a06c1de14b52074623bfc153b5f26151a0e87e2ccd718115ba9a360e0973d1ce7f07d7728fc28e8d9a14ced3876a38d7575a80e0f8cd1120b6e6c0cb9c29cf9785b68abe7174d7169dd3476b24f79f720df82073345dec282a0d20a36dd01c45f799b12984cf988f218ee1ab62d36488fedd938012bb66004a88b6d2d15af07e9d87edaab920aa1590b10159fe95eee8512e43d6f3c93d36366eb5fe82395637e2c29907f882e52e3bf72c3decc494b7e5875f46c050780d6161b5e6fa0718212170645e7eb3548e29d83da6aa88f168b70510a09e7512760a3faea48dce38c8083f674e46e200c538f89d4a5008c61cc8a548a85215c9430f9fd3efb67cdb75993e1801adfe7b2dcb9960d76080dd56ceda89f437aba22c4f35e336a37f0c0f08be0aa93ab5e33302eada7bc039ed40bb5708414b93860c8c1d96fd2f43471229364f9d599ea55c2511bc88357ca2edbc3337061f9eaa63d1aa7a526cc9f1183ed357430734e0f9de5787d7f11e727add4117e6891a7ee387d5749f2a4bd115d90e291b769600815b6e8db84273fe5226cd86974dc88ca7534bd2e1ea1e1297b5d2c7b963861f330ae0084425051dc70f194e6962619542b0c342feff5f3e79a027e92d40f60449b1cbe61678d5b2c69aa2d644b165a9d1b91cfce7069898a72561451bdb6e9004a9cf185bce70008a97af9f46d98ecb23ddd75473a182fd0f4b6d311621d2a7e8b267a1e5cbd24d34b77dca480475f3852218063b4adf5a30e9f57a67bb6ccb2f73f083d921bc470e6fb40f733a40c1235fc13789ca49b4da6723711280241af59aa4f796f8cb586c726aac88871381ea327e95ff1346421ead23e3f2d0f364f3a3c41674ee15d8a30a704db263396ab81cfc2e147d9902e760237b93a9b046e8a71c840cb968902229e96c2c8cff40ccdac3bc7acd05fb7d53fd1bb0a1641a12f2fb20ab1a91a906224cd275b9d4d7103cb2c2c0d0be5c9073d909ea83e670be3bd29ee986c07503f4f59db905c33175c9e9d77183c9769ec9872a098bf74ba36a897edc9c9ca46cdc56d78a181ddbd1cec5c16bab19c5ebc43e8bdf623e1ea0726ace6cc87104d01e42a318125370a77ccefe06a48bd84ba908b9002d7decaad934ddd16811f57cd6d7901d76e74490aed6a6dbcdcd29ad4eaa71d675a9f208251bc22f6240dd76170156b097b03e7a7046576c20164c63ffa346a9713f76eb42ac6d47e61e4a44c6c02b0982c2f20767fee26c05bb04192fd866f4c7861a4b70579ab68e8de47527b3957777e8a61b94864f3300c97d4729ddfbcbb627720cfe97d9decbffb327d7afe5070950d0dcd268e79057343e82304bcc8bcd3deb630c562ef1db1b7b26980296b41dcd462ec653e48472685cfe406e199e2663217723963dd9e36909eae3777f4ec88265d38fd0d1fa7d4530b4589bf28c300e236336687af5dcb6eb2c97561de923e6101a7187b539e7e81e47d233ae97d19e56b469102f0c63d31401e31add910b679c85f4c8fb4be4cb9afbfbe9390773a32cf3e2881d374736684ade7bae36f416eba0e21e7a7d33be1ee1a9303f7eef1ca56241884491e5d1cedc373d7d1d59aef5f237d373c8486a820cd4f3a2b93495b04d09878a590b850bf885461e1a97f12eddbe243dd0aca0351223939526350b4a53f37592a076cddbe3f02db7d6519fe649f1b9197294450ac7ab1eb66852c338405045150b9e2789fa9dad2ce1851055d6492de505eea3fcb34278282c21af08fe509276c5bbbc5109a403dbb7b76d34e43b351926929b6bc62275ff4b1839e430f9f4cde29f8dd4f881532a7e7cf6dec40dbf16813230ade4303891615e40dd57e20922c105327533efd7d8a1e199e53337abf6e7234848d481f78b5c3ecc1e5ce29d15ac52b2de5f0dcdb61e23787db136474fb83d1c6f899860fe978c84deb2931d37b880f81912a4dc0a235c817b340e97df8478dfdfd2cdaac5d8a1e6b012ee0724d9c7891386f311da5a90db8f1ea89e76cfbc1ca876c9f4d5f9eaafd8f059a61c39eed44832cbff34e25b5ac3793f6f2a791916d61d1a8b8cea2531438494f9deaf3c06a8788ee94bfe0cac6bed406992dcd321ea8b33ab479de6e33efca50c7fb12e28baf5f5a38e0c877ba1ce78bc95c0176936669243e3d5e2875001de1637203288073f78a64f2694cfdae0aed658e8989d965e6243a1046d2e320ed6ee9175cb4b7cb5e22b6373ed45c79fdce85102855ca22ea934c283fd06172a2b934b68fab3000120dbe2514528a2e0817ad7b745bc999925f5c8389197b9b67012c38537db593a64e9c1986334b4987c3172e780d8ef1eeccc2f8def0b6c1be5e7200c50912277cbd5fadabd066b52286490009964baa9d66ec5227096f9a9a76fdc18e23e91d0fd5fd16553e5a94bf884910e5e6bd678f50cc2adbf1601e8093d2445ecf927e3ca8876237f393e4204141a88fb2a74bbfc5baa10d90343cc23b8724b3a6e5458bf7521e23e063fb79b650e50896c9841f840996ea099564fb230e093647db206588cdbbd666a9af5795022ddc549b58994a78b5bfb4d0ad7eb3342efcb71ae7a21714e3fa8b4a42b532d02780255ccf1afd89d775c6de70bad97b85fc8c742886cf2c2a429b0fab65cd976c1db3a4741a9b968c4863dcfcb3d09ca44c5c0721998a565fd9b6fcec992cbb92cf43581a01575e0e8367444f8cdc73f477beb867266aa7cbc9af2b6d3b3272b6a82a79a0e97746196c5eb71195686ced43ae3b3e1778d16c7069fb3b90190382bd8f60f25772390ad3fb0c3d161659371128d73f901e32a82e0133d0ec14b2ad67ae8b701ab76a266b862d3f04edd043e51e5a1dafac709cf3859ec59a8c606368d8111c9b0ba0483105570a060a8466215a06c6d49c0ca58a8b6490c830e2b075056b370982f1aa025119ab07deef315db3175bafa75750caf07bd190012ee163aa143365f1e866a917234b684cc7d5901d568aa852572eb2070160b826266ba6433b365acca49e7f9c5f4098c1abc8e5722e00c30e89b7e4d8325bfb82c8354dc0a4af551387bded3b0940c015baacc1d2cf083d55184f141b7c6f36817a95b8de67261dca1d5b635411c9f7cdab8477dfe2dc2da997a664f6928eb48bdc1a4b8d83533f0acc61b384e5289f4ae672ae84bb4676b3d285703aa1e4a8778c3e320505b5be0e6ef349b85c62ba8c42335c425c6569548aa301c916b672b5952a6e083524b201b2c07ebdf4e2b576ee4fc4dd96b7bfdbb44f2ebc0a0fc8401386804f238586127f76660c3210ff64943b97ea0ac870d4688575255d6a2864d5996bb2dd6df878e571094a17bdc5b6fcd0e1b1cbe17c0b86df7b3525e2be6e55e4fd186d51416fa0e1abcab35aa344e8607fcb444db18e36e6b05adda413c4336db44c9a275ca032b052f70c37723f8a69c5901d604091c72841aaa5ae43a19140aaae638c28278a9d75fb471b06a19d5bf26c481254f9208d69f056e6ab8a17be870f4cdbe79490ad460f51534983ce1add13e7a5a78317df383e802b8df2e9da892a9970f1cb4405dd7ec8c4d77ed7093d925825c02813ddfce4acc4cdf9e7bbec7e46a64bd0ad8be7f0a5ebeba8b9fba7704710a7b56d835d0ce4875cd7dbc879290ea6a0c1cd298e7a995f4c673c4e55d3c9973612b194e1fd05aff498b83acf9899801506e0ff8b3c9a2cb413221be948688bc943d6fada86e3387bdf3fe07b2751072a4ccfa3fc9fadc7274798f3156a380071922cfe1240ad313ae96783def5cf97bd1ddf523f7990d7fa03231c35d9f4f26b31232a78c3d9b3ae9ce6a00bddb869a0520b1acd7b4f137820c647f2a3d848da581374678fd60112d10d326b12be678e586bfa65cf7ef82320304024dff6806a58cd6410b1b2a69618d6494ca47484a25ff358d4cc0ef9e9f2202b580b16179c519cd3a4c441304a7c62ac0c01469aa34b1b24826ae832848baf151bc92441083e3d1df626e567d67c03b59a5a65c325bdd505268a43d2517b387138f15d03c9ee7f397b60ad3273b7848596fafaa266ec28436bf01000d5ba0ed39c42c191efa08f270732b0d88d2962b662494b6277459790b75c7f10b32dc1c661b34ef24953003c974b1e5950d7835114602dd9c545db8f60abce4517b0c193d484509a55dcb1c0a26f3c50359e11ffb0bd05298596b4f3491f191534a988e87371ae0795d1bc9e518c768d4cd2db4716c63264efaf0dcea71e4b7d8a0ab9c99daa6b4c99e71b83907957e5f9e97720f9cd1042821edf3ce98a46defa06e2bd732c68b1715d8988d8afead12c02991a1b4f2ea638a4c5d94a287f37fc1f96c6d91ef3b043b74e77aa794d8ddf963e154f7709a2cd980c06b32bc435accc0905b125bf81b3b21dd74eb10f2829b175042e23618ee2e54c317f79bf3e47e864e373d589a0afa26d26607626fee37121cccf78e51f8bc582b7dd4bf4651f7b780cc9d325e197352970bbf53a2f6b4ca0caaf171f1b75b956143db7daf7353d356cba4b3e0a8dca58ed4e36a8f8f761126300881903fe0cc0c93799d31976c2c31324ee0f31bfa705b87a021a77bf2f1a2e8e5e3cec9ced8c7fb7812f9f027c6f3dbf12f2c39fd7d4802a04de378e6ab2bd60513fe13b80ad34d59f40cc0627af5482676b7adad40c1f3f2185d676a82bd9314436531669446082db499fde6bca2db21204d0b9fd28ecbec021e1343a7300cc6441d7c62641d3ec338820fc331969467b5e1c89b089234bb4af75b9818da3bc282f4e7212da5612f9114691695bcfa79fd1d7d97083c6d68a0eb2b2671dc6e906f3a4362be1b8731d8323a484de55b985ec8a6a489b31eaac97f6029ff65","isRememberEnabled":true,"rememberDurationInDays":0,"staticryptSaltUniqueVariableName":"e58622878c5b4107a5c053c29b821537"};
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
