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

        
        const staticryptConfig = {"staticryptEncryptedMsgUniqueVariableName":"7fa1809616ffc07fbbe0a24003422d43e6f94eb48ea5fa9d480939ea0437d0a4be59dac8e783531336e67def435396c6e6ac27a1864e8a1c8a6082e47d58705826a218860c4c45895fda23d92eddabd53b8b4f0471e0126ed350b652a9fa32066198e2ebb7aad3645b79b59d1d3540826911e244682be98c4971f2b5307dacee6d9400f1c1e10ea9cfe2a17e4b4505fad1a0a925f6b92bc1ce6c2ba9b96659eaf33fb89a091fce97005bfb70b66def28d7c390f450164c3043bb8aa5224fc850ed31ef3dd6ed87a84f4571b3f84a7aefdc4f2432372d3d95f3cf02d859d03a165cd7252677739e2ae51296a9462b247026a0b51dca3166249687c5e8420ceaca4c18b48ea8db0ea7ff0da137492accfc901d33c74b06af6544a76b74fdc5a17831fbec14531cb5ca6675633298d01b55dd9fc8b54155ab956ca953cf476df1d704898a3ea01cf454f732c54e8d9e5dad6f831cce66166c3d512795761c74413a8da0d1c644060edb319d46db6e8da6089ad39d1d6e31d89140fb81c52cd295266ff97643eae5cd98bb6cce2e7ad313e6bf6398edf4348a70f7b5c76c081913a55fcc4bb89a153da59fbd431382a01ff9cdc6449dcd23da9786a8a03fe794c3dacfeb81fdc6becdcea75ffc3c008d484f46856f3270b649905bada3ab0086077a0ee089962ff0ce0e33ae90efb9628753520585b2bb25b53a6da87a7a5a0b1d3b653391c9ffa579deb5edb031e7507a519ccc08ccdb0e187588948314b607dbb16d48abc08779f3d6b0b5f4229b2528516d9f0f63885e21046d021c553fc4f42df4fc4dd785a25300468314d4bb1c9beb863566263980892fe36dcf480a696a37ebe78d88e2db4518edaba9c029e2820b2481ea02d01f3a17228101d23effe82ecefc5eefe048866e149a31a409d4ff3a3c5d98436a0127d7352056d4ca57c0f98eaa724806b1e0c7a3dae1271c432329cb6bb77827db980f50300ce562e179b3dea31a1efc5e137e99a1991ccc120cc68f16f055a90131b2a2e6d21317827712b91817158b1a2faf1b8d3e0a0c554a6f0132ba3b0d9bad144997017aa36bf84fccf3c70f0ee8e34b152dadf96e399fbaa000166ca7d9cda02483b87deaefccc473330cb6d91450882c4eb31310343c9513a9022aa52db2702cd45ea712e52d24945c73d69212dc61b8ea85d5a95520dca340fb3939d96b289977eedb89400899d383a77792a2f1ac1db2567142b3ffea6822794dbec059ec6f9431e0571b8df8b0059e957b1f6bd91e21a6563f4ab3d6e5f7942e32251ec312360d2d3ee79684ff06c5ec2e1851a79da34bbf67380eeb87c0b2e03b0414d4f27929a7f78669ede03aa5687b3a38b39e136e4d47a2d8c55b1794abdd96de7404d07dcdfd4264d48c61a9c3652ef76e7946fc241ce32a97ff7d3e40bb1aa37bbb201103c6fd74c4c3cfae05633b1dfc7eba4272db0f8b152626cfdbb4f4092065b91436b8d638c11ea5092cfc01a5d83647999a872e7835cb1016298fb6cf76177c02f9dafb986cde970e1b817f7b724bf09e56a55f233e7d019a8975fb393aa8742ea8c52f1bef3fda38a1a313b04eb274f98aba4f2e925c362a11b1575944e87a36dd951030d4931893c7e5aa5d392a5af723908125cb537c13a880ff4512202a1362058a6a8528b5575321621132c67a62e2b5a319af68f09186cf29fe6f12d14cefb2c8a3780368fc6af41ffc8f354921c95a07a714b58b792bb7de02e58aeb28f1865eafc392562fc42c17a0d249f44855d9c7fc61605eb7073589c7c3362523287c5361cd84d4f59a82882b7799ed4e0167897185e498791a1bda9e2042af5b960f50727c8fd184e117c42ab9cf5ec3ae30a692fce11f30d22443c287cedd5d70ee5e7ed7bdae010a6534b1dcd953b2670f93556b0c2e91558c006dc369f3eb33e637895fc8b454e93e11572f9f405e1fbd1d243f2d5ed104d7b6cef5ccece1dde3675f446bea02564a7f1a36124b108dfbe95eecd9c2a90fee07d67800180d8444c7507f0b308cb6b455eca8eca78c5adad7a7fdc11bc92b3baaeea9894504eae3b0fc93e27f9dfc8c03c7425ddd83684f0d34db885959f3077a603662cb4f1b2a282ba942e4293f26194699b02ec713fd12a07344eb8725e0706d21a0306ec29989a73de5db9408eafa27cf680a4bccd5d3464f9a14f532131e30efce2855e06a14c4391b2d59da1aef74086d4c4ac3ae9f526c43814cdddefe560cc655459b11a1b0bb105b8b4d3690b6d8a532f765166685a77c8da4ab22be26b65779f767dc485d810881084294766e7d1530edbff144b1e3018c4b6625ac18a4907f82673033fb65cb2b68e44c0c0a96843dd3bf263ebfa80315fc9763e9f8e0b830bcbd196c315e88d62c8b354b774cf6069227728a6cb72b4ed16dbda11c7263457deb4aa87ebe082d780770951a3e9de525ee0f97fd34c9075fec384ce21256df50077244c3908d2c49916d787a9aa1186efa48044d35ef5d887725d3e256e193070b758a296d97818235fff413cb833291c7535b201daa4c1b805cf9d0b470d2d6e7f0927c03663bddd8a049894834e0b61f5efe3476dffbea163b8402fc7c1b9d5d2f7f6c8571b0e7b0280a886cd17c2186d3100b3ab634c9797a9bca49437f8cc7cea43bf81b312ba2ea257873df202c697f3fc411ef460c757daa6191325a83776193dde7aa8914544cec5d0212f5eb3ea96dfe269d110782b6359a70df6aba32a392c4eb4e0121ee235e319b134bc8f63ff92b6e72e3459435ea75464a1d9e1afb695a632bf9076d6c716ae92ad23d8fb20b7b2afd86a6a8176144d92bbecc060ee46ba65dbcbe14ede69710d4ac38e553b5283b07640adc6ac9c66529bc51db2f3de478882699736bb8fb1b93be8211c1d26cca146f4f95e25d9b15f6ad528370a82b47861d4615b90b91af61df32890f68d72f758563a5d0c73a965cfbba1d897c883e7c4979276041bae1a9c8a4d2612682e63bd16d708f086063afbfec514ab98e5aab91167e0fc7c2ed8a46b4ac0997914a9ffc5296fa57c80c8e78a7ba825b98ca9ba8bc302fee8626c949952a52490a58b4e8d371cfadecab8ab257930458cf21308fdc38497ba08b016590a5009afc2bae09dd65c22a7b7dbc4d18e4a4db13025083a7c9b9f5694f29615d208f71adf5be7f6894d52e2f56d563364e69d400f1a6622ef2f7ae1cd090affcb126ba83cfb13d8ff1bbfe96fa387a59c059886b54103c8621ab8e321f001104c828ab20403e33c6d149b6163d13a032aa4ebd17d330ff5908f6e2b1937d30879c2e5b210154775a07331dc88a28d5555612ddf983a1dde27fc06aba708277fd86f84c1c225235afda62bd51be1641d3a96feee433b8292969b9513375bfaaa94e801a39840bd8d6b5b9a3a0138d973c67ee9b5ecc7f8782b7d7e89a6b444ed12eaf797ceb6e726db3e8a07f05d9fdbb02998f8ea7e30eaead2a27169c85e4ea30d19a5d2f96cf68ade10045df28fc2a2f1e33bb5ea07eec7c18bf56814a623ddd6d353b2bf2f2c2a342cfafa26985dc0f0938d66356c3ded416b9018c9faf44adcee2532a816826de0efd3c866899c1528eeb1f4c06c388f3333ed55e0ee1e1a47de0300f3bb540cd877027a9b80a8608b1450b7e928bc58a0e278b7609c684132e2cdf30f79fc7b03b2c0bbc8037cbac08954f8c906bcf230e7e75d2c4e147829f1e2e5a4285b0820f62669859dbdd07ad112c1826d112082a726aaf60c740bcdd7c36f8c4c6d1e018acf031e21fa552b08d14cd4c092db1f651330eb015456a2e6ac300b8b9e85f6b4f6db2c9746d524542eb45c52960519917fe5cb5148bb25fd67eb0a2d5ad713c6f482cf2cad959bcfad0fe67b600a1bae2c98a68eb46764c9e6865a32fa9f09fa10272eccc9f0f7da413493e5a937fa224ca99132d67b8a0dbe6621ff35039c803b48c18ef3175961a52daf03c54793b350d973d9c2ed14f529eb3659c5c70b5bad6fc54a6351e314b0a84abe94e2d8f8f461b9653d5f8a85408a4823322be99c10afa1dd4256b2e54183b6f89acc40343241ff6614f07d9493b720f024f8d33c3876b7ca396e11facc3c28b8d124a7bbce3e5d83a9cf679c6c4977570b4ba294030950a41523459734f88a11e3242762da3442f5d10920839adba3914316e6c689828f36f4ad1d319421d8ebccd336201b72a01754f21013d368e441209063f4a97f6ce1b6a4ba45994655224060be6d57071dff2023ef4248d8c41ddb163ae33892b89d1b3e0460eb17f70b0570d17bc592d7e482a04b7d59f64b3466034c57b1dd6263c8f0ecaa9c8b27875f88e13fe3d292ecb55933dbb7b01beb0cab6f1ad541867ee9f7e7044f9f0ea5646597ca3c08f581be1dafdba211600f081771e8a5a4f84f10f028763b3c1d12048212cd8dad95868900e31004c337b62d10f54ed67914522de8fcd1e2f271ddf369baa9c3c3a7c2bf88f989590141cd79aec7c6c3ad67a68288ec1401b8a255513994b60ddbf11774dba33ede8b06d2c38634a66f37da14332dfbb7018013c73e47f9a0e0acd36b19b58bdfa404b3c7ac99738505dd0ca7b200a74dab68427c78f1e0f78af92b4e0a2af8fc74044bf19a579bb0940e27a453e10d4befa529bf60525777ef83d9e8b84917b92b91dd7a7f88c5154f628f31637c3fde811c6fb314914ea40efe5a0694a244493759928422203d623dd692ba4d39640de417609bb0130c430a00e7c6ac8be185b6010dce81e43558d0e24661952c9e54691c723771255e04854df948af042a28c628076a095d5f36c38caff7239b4260c626c1e18f3bcc2af4edb31152981535d3a6aa7c9c56952f049a8bd05fe4a212cfe00811b0cb3c13a6a64a8f756956975116df883eacb0191cf6baf66675bbe9c5ac8ddf50263269774c73dc33932a21bcf930ab8fbf104db6e26571b7e7f523f61618ce27021bfc62347b74a85160698c14d76e6c503b269ff6802e100068a99fa4dd95a3c22d85f58dfc2779cda9b14ed204066c716dcd629fe01153ec263809d15cbec6d94e14728d4af44bb0bad5542a25d586a81256ab11e723f0ff279a43219f3ec558474f24aedd632b068e60a4338879fadc64fa0e6b7125c5c02135936da86fce8c27bd17b697795392347f181245b37947131218034e62dbbe018697f1ee31ddabc2c80b2f3f339904812555af6d7fe1862cb71afc0ddbedd7e48fd3a51fc0c8895773c08f2bb2d5d4345cec83159a2fd729c630478cc052c619c9bd355ef7672f45c53b6f35206b5fcefd854802a344dd04c539415986832d8311bbf4db5a220c2b27f4cc5467b59b8075c3e0a4cf480a8155d121f9e4aa3cceebadb919138c710b9d8f5c947cd191eed14285270c4a17ef39d76e1c0c10a95d7fc9f5989a387ae6a7970e6ca0dccf185b349e51a650b9e885d92fcdf909928b8f670a5706cc2bb3f386b5d90a787c94391db529dce671159a1d0b584f44a50895b7d0aef08620637c56c144bb86034c1b2b1deaae72f24ab92278c1feb0dfed295484b94a5a47592450abdca212d15a1c57c0dc7dd9f56d47eb34612bf956fd408ab2d18379512ff52395957e7756a37df5a9c31313209fb12fa6b818ba992c3a863ff69e783f3234ac05bab149cd43255c53c74a57c409bcaabb7426d0b1d1b52ab0d130be350844b2cb092d19b7e8f7486795f343416b8795054881d78d2539b5023b05c6e27a0ccf35214a2209820435468f1a9589cf309bb8e3307d7652cd4eaab1215aa7b2fbf9caefe6aa2d5b9871e4347798ebace652c819e1dcdff52da48c86b64406e815532f32a54158716c21398b45efedffb47c38ffab2c024f6e2266a9aba10897facadd6e87a3255d572b4ec5086ee125aa2d3b57227db6077a9643b0595372367a17a0e39f6abaefa23e5ffda1cf15d1f06338a15c5d0951da6541dcd36f135089c04948f7eaa87e25c9c63a681621c233b5ee4c44d7621578f2eac6ca994d168ede56eeb1863fcf90fd38a95357691792a4ab0758dbb402a6b304dd1cf6a7d96c33d98906026728f7f7d63c5d5f3557919857e739b4e625c1205be1e1eb0bdaff9bcdcc6caa41bfca3c5317846bb88f4c7750476145f897f7250fb338ed05e401a0f168c32741653ad29743c3542d104830c9f4a04ce7248744b34ad47c6f110894f56cbb575202b96a1d2043d7e690001313d6588663270324bf52fccea0d83e68eef16d4fd6477dc9870f57bd069ca968b73ac0c2a3a481017011bdd403ca8859a6a1ae1a988a51a9e0b1410071c7ff04fca0530f5a5ec28fde091eb9594d4e882460cea075a536dc4cabb19cde917d74bc4a4a1bef0ac5c2776a0d88685841f7469551190f162a324d2359394fb1b62e8e76bc9a11bb469f7851c571e6129f2bd5bdfc16e4825d0577f450b059d9bc53b62721bea3157e245a9e569b1920e4260857285e54f7a1f825b54c16a376f62e6c66d70e1a8e8ad054e3fdca64e00fa3a13cdef8f460e562aef96b013456ddfe1feab8bc5abaf3cf135d42659d7f1bedc208bb16d8fb91e60ff8f5d42ff9297b18a9fe3bcebe33eb7d290c6bb9a737ebbd4c2e94c64990099da302436aa51f49066a0637904060348ab645df90769873367a954e76ae1ae0bd1ed0fd3ebf89d545a86ea40b691a12ce68459b86113b1f883eed10aeb3a60e884a03835c46913f335d9e7eee6790f049afe8240110ef4f479287435e13705bc7afd7673c0258d629b5f7e1e5bd3b69c3977d08f2cef11509bea8e66b76ab11224cb03dac17d5d4cf245b6bab0d001e830d6d2178d6c821bd9b7172b83e92706d474a98fe117ae369358d638f36408c9c5c79f80d3e836bc560c809ad40790bc42400122bb3a4bb5f830e28e67c311eebb3ac1f6d752ad45e99d5b0a4499ba9668beaa74bf44740036ad40c9ea4d246c7f503807a6117721a1929de20837ef70afda5077190ead2da43e8e2ac8820bc8238714e37bdc624fe0d8fdf3dbe90fa65b8e40c82fe2758fce19a374c03d3113e040219612f0b996a32ec4a69198a5eb71aa1e147d7c17fe0376e7dd5785f6ac8afcb66348f34646381978ef2507ef159345573dab0e14a57eff50aecef56dda050e4ebcbf142412c5ef0f3b4ebb00759d0a4f69c3d58558a89d761535addd53f5fd56ae09814110959255b00b88e234e42e70738f29e146e4cbe7219c3f2dd8c5264ec17f79264ac190b5dad303092030a9776a637badec38b3275609c6ab4f1d6efd3186f99b0290976425522bcada6c844432d464c4e64f999dd201181b17a88f69f62ca401bf7025ef61d6e98e67d685b2cd9e46c56ff26fbf4a30b0da49779ba7b5dc50b99a120ece81f25ac24124ffdff9cbd6c88142edbb74e77cc4830d74c46808ff29c83bd30194b8a339eee037e96f22727e1a3167034e201490c152b8941e5686a8c90dcfc920b48cddf4fb40f0dcfc553f212414c10eb45ef2d2b457623f965c5e923838b91b86cdcb6be2924334125e7c6cfcb9343b457c281cdc595f60b546af3121ab46f9f9dfa5bdaac80ba1110833a1bdf04eb5155c9eb73f95d9bbf9246e9b45c622216e2cc080a6b6ff2d88a485744e66aa2efe724d39db3dc7b5fb4f3b1b3a2852e877b90132c978e57a0b2ca53a431df4cd5fe0baafd4847d7a472006d45985205a2210ebb6d7727cb42c077ca17e87c73971bdd0854ef20dba465264f229f6f5e2dcea06ca243a13d987b11b599e4a4b559e768aa94928ff64ae7c4fc7abee2b5dc8f4f64f966c831eb2928cd1f963857b5505ee8eba121e8e267f39b4ff805976593d39677ef3843853c4e9aaf19ea56f206a0dd8664702b0723f88fe8ebf20d9c86eaf71a5d69fc5475d69cbc9e4f40b23d820a0fe626be0146b29a288bd71face6357e78125271ed5a2b22f9b096b6653132172e921ad6a5f8464250144e690ac702d296d598317fb2b246b88107492eba5ab5c262990c6eef1b853e95ad7fd86ffe4a0e50cb10676b6e52ef4fd30b3b18634ac8e38ba41622c9ce5e0e8935be4180e00d8cb8656f1820c57189e176832c9ff8f99c2ca5a445a526b72ced09efd18b0e17a4b30f4ce91c9fc982d0923191632ea6393d78590c5a7ecd51dc895113e0c1e6e317d2dc97c22290017bb242c028f41e454e0670e3475fe79f42f7f55b3d83abd1736f3bad3222c36b7fd54960eaf9cd0a5db2fc4b34f8a45ca029650b9b4000417093be1c0e2bf26f9628893e2f6e0199020e5d4afaa2e6bd9a14e236e017cb1db677b8949e1eaa8bb070a9a77322729910db520d8b1d2866da38a31c74648e95cb690f088f34f08b3dca2a61c0182e4076220a379970917e6470bb295a9bc9392a179101297bc966a0b3961f47bca8899c45c6bcb8bd444fe8e19221205cb3e2d5a630e5c60faeeb5682239851ea4b1f31e1967276428df2ce8a7c416617a52ceb551ec9965aa47fa1724ace755f64abac013265d2e5c08329eb9036eb73dc44955f77d662aa1b23f5ffedd205f1c4f2e0e6291193103308c29841bb2b3269c393cfb1e5919ee50773c04f9c1139a8aaf95a921b7bdb914201587a1f2498d9eb25e06ce8692ba400b430479540ed701e6a4fa04c74b2480fb0d49d53f5d7d9d2760e5f6623dd2219d80ad907199e3f6e8aa6ecbf78c111d033509855913b9f7d17c5a2aae660ff7a3f3a1ca5819ba407d4aa7721540623e1bbd0b90c9e46f8a8f1166b2999595b637deb9eae67eec9a9ce3bdf5c0cde6dac26aa24db4f2f257ccb495ff8008dd6a436ab637e7cabd25733debb1b43f1436770a4a5af75eb1d45211668d3ed221c21c712d00abc3ba1fef7cf790d67416afa84d783f9fdfdd124cfd54118ec0aa548daad6080d3b6e3981a0b11b18c44e7d9d0d85accf8969973943d1c1f0878f00c0b621ebac08e1f59078be67bb4210ed34661639947491b861eb45d91f26ab7818bd02193b27514fd5acb920d1ad514fa9e79a63ef0f30791b7729d4b1ff5399cd1473dfbb2cbcc37a630ade64ba094d9a0c0874792bf526e7dd999efa5a574cdf21c9cd00450b8c9158ea5dd9e26bf4a2a8a1febeebbd96dc741da4fa1c7676fb243de3255e35034e4a3866a9f45f5e09ec6533029bf184a9e7da6ea910fefc61ef8b4b61a9021b6b0896477c1d0a5d1105789fb1abc16ffd11eda24bef9076814fd5334e0b5bd678d117f3e95a6f6de80a42fbae410b51d06630ddc7237c3d5ddb4f5dad18775093651f0d46b4ebabdb00a564979464439c1029a53c8a0d0b575f19fd9713a324b11ae4c7b3fe69ac178f24119a556c199a3a20aed57691eb384c52ed29dfab168e3810b50e23b16b7b551d626b630813c0db98c0c3610223c57cf25a0ff518e6ab179fe3c943b58e694761717f7d673bfdd46a46580264222a698618b243f739e722b676f5a3896058db35f26961735fd7e53b72184f05123bcf7ff6d5f32b54912112abfa1ed67ce203d232c56804cdd0c791a71b1f148018c259eb186b423987f24907400125964a69c8f57dc4148fc37ffabe08d4f05b55c8e2564a4da93ad09581709d64565a22cd6aa7d07f26749c0297822c9bcd86a9dda3652387adf46606ef7dc07e80b891d1d30fde8384028dbfb61595a2fcc650f13fc4f8102aa049986dcb8fb142201a6e45e94065e77ca950228a15a325789d3f531844c14268e1c241e4e63d842063fe5e706041bc45ae159034f77698b8b9b6f6361607a20d447b00d6a6cc1d776c84989c03b97bc4b829d43fc8d519014a1f259dbf126197aa67ed4b879c7b7fe248145abff674c7aaaa165c5ccd5b0c6a1776c50fd93dabe90996561a17e52893741a1da4597814fa4523cf75d896e72a71ba00788eece1529b29f06af520364d74411dd09923d0cc2c688fea4c32d39606a2cf1a935ec17fd01dd117972ac713cfe16e92ad60dc61f33c169d6a8b764e91000cd4d9bfb5b8c2985e2070302ad59afa5bb6a8b546e2b8f9dc8d8d2aec7c58b68664c337b33e177576832a9d3ae1cf720f82650582bfe1b180b808b48c54a430470e8fbd0727aaaaa8d7f96420a2fcbb766818f1f752e84129122402914e83647d6d078d149b1665b331ad2527b24637b9e825534c3d219c55076497ad4bbbb5a5bc13e57acca72f9e658ee1cf52239104f549bf2a9e1d838efb8e32575d5fd1cc8c62fc429755c599f519a3ac7e72b8b6aa2c3ac1ed532947bce453a59eef8a1c4f985f488bdfb3fb3b408d777ef4c0670ce45d9aac0df36638f1fa0fd285027309dcece88a8dc9600c1715e0114d66492dce5486ad505da7c1a7903353d8f819f826e6b62d056dd648d6c283d384d161b8231a34d9154e709232716d4935f793e00579d2b61428006513e9369e09af47484e8548f20f9a4b4e738c495f4c09a3238a7d3f1bcafc2a33086bc308657a60e6ea26d028d566dbac67e695fb33e831046c366481e192c32b6dd3b5395af4a12aa0c16e114e65df61e498655e7bcd9dbf1a188bce7480a31568e4afb74f7952f18e42410dafd9969ce822ee38b0b972e4a1aab5c4fd375a10e32629f916f4df78018669457ae712219d5ede473c2a39ad566d0d194b7d4a776972fe15b7d92aa8a1b0e88fcb92401cff98acb71b9b8e3716df2d5f32641f2234e774de4dcd1f79b8d42f0b542ed5c983bf514828ad1c9022e119f6a425255459109eaf55d617b731acf8b536b74e3335f592d49e45d1cd5d836cf4ea6bd2d7bb592326edec0b5532a3e8a3bcf8fe67a4d161f304f020ebc049ff0d565fcce8614e09982039593b112c5deb174cf5a3d1610ad51e98e9800e953b80769ea9f1df3ff3fcd073d8177fd39df7f2c155f68d267dd1038b99da9724cd5b95599331258c494167e841de862b9da129392af66d5e997979de20f24416ddb52f1bb28055109919eeb01c63768058b26555a081d89a007ec32e0ec15bc355f4abb6a39801367570042c3f33e8683949869ed0688c150209c883cd7104a5d83370cbbdc0aa65ba2448bf5d290e5dc4f6413a5d2a34f7a6d3863e231b317fb601d06a176dd83c9bf0835748e439eb551e00ce6230083afb1fce7b411798bf9f1de8b23218b9a346e3c34781705b3d8ab1d14b7b39541835141d8f2d1ae4dd5415d7fa2795509ba893e684fd36f82d895be187666356a47e356c2683919b8391c3daf35ea1e93c542a6a4c251480fcf81731bcbc9634c8c705e3f19e147cf86a0820f7a29220ba16df63b42fb8df68884d84deb877db7e50515579985873af60e03071b7b39c9fdebaaa8b8483b2cf2435f2fe574af9c107e3ed88d652d6b1a39f40f20c8276e66f92e49ed42b801a5be25a013257420cbcd5253896e6f2d279a0c0ed3b7062753c041f6e276327d2865697547cafe2dcb7e93142d0f4d00bd454ad41e3a8a924b95337664e8d6da7b8198d3a11176911a961dddae5bc6423b8a758071d2ed97920a3e5435ae4fc8c2711ca3e34565dc5a92f221cc8366e8084271b6ff8439f268d8c843c9383f5364fef0d6a7f3b553fa33ea2df083e476c7b333960286c303ca98f1512b60689a82175555c2691330246a3b92886baffc44c89fe75b146d459eb85f379c810b995ab2556e196b64bfbf91a03708ea13e0e62553a327d97915402b4dbf2aa25c415e481e5da14ddb6525e088b702df345a0f824f18ce8e202e5c6bee33ee7bff177e4b943ff011d1123e6fe88dd4ad696376d4a42f062d15805486864d8f98badf3f477593ddfaf1084586b521e6da51f3accbb6d46cfcbf29c236694e5789939f7f6868de30117d5ef3be0f4d7f91ce1f0b40cae4da690b04f516666beac56d83275c6a16f3b44770d24f4e7fe7ca1640e8f1174d263caf89d314f1f7555917597743f4d0798f90231e20b3b485084477e4acd9dd5156fc2d79e0f4264499377fbec96208da588c3a7ad1bec0e769786e20740022d45fc7d72721da71eed6b0014f026cc5361e2900db6149b041dfc16df0db9cbb6fa20c9ac543c4beb30009b1d53362ff2f85604bc70dbafc5a14f52e2952b0c7dafa060888e05959752bbe35c7a9756a135d84ed16deb64b70ba44934894c6aa785707e63f424319f091dc17ec21a16e9933f5eb15f7800740cea31247495126562bafec3b2529d170cec58dddb266c70bc5f88599895417379965153371bbeb2071fe44b22c2ad263af95dc95e74ff81b20aef2218c64b5866b19c20133797855dd251228b4fd5439e7967a730394269b23e598620bc929002ab2fd034b318e0665b794509f7f897baaaeedb6f6075a35d8b10053977af0988f32ce3fd1d67cd2cea9edcd76a4531d064e7dfc830f3f274a919886cde51047286fbfdc90a02c926b0f530919556831717e834def3def10047c1e04ad54a4e9cacdec730c0c4c43b2d1f6692a6474a4f906ab001884d54c080d932c74f3ab56a8916b360896ab52dc422a5089468186ffd4bb2b816b543298a0f9d4429dd635abce579330cd8418d65027e923a98d22aa30acd58dcbcf2bbf71701aad18f7316de143cbecd873d8b9c0a8590912a66eebf33d0e47dcb2eb548bcf8ed1d29d2127d33e40316003e30a5b1eef36f99196ff2cfcd0a4cff4d20a6ead9e46af5544a67e166b05bf8a6b41fd75f17aff15d25969e8ae65f0506e99b957e8e04d5d7892a13e079d03277acf79a1119aea6c9e711eb57e0b3e4d5cc0113a9874b1d3cba4bfe9315ca26a32cb25447a5a5c446104c6ab835483cf9ff82c3c930849edfcd39757eaaa6195c53f5faef6f05fd1be31a307439b6c4ad068a437731dcc3c7273c8f6b928df0f281ab965eb34dfa8180789de1add0902ab16afa90b2732cf26c63cb9c3c64396dff6140cba63ef2b7be582610fd5f19fd1124eac656ccceea291e04aed6ee82250560c48dd80f6916d2f28ebc0f7a38303925fc8b6562c1e8a3a5f75bb946c6d39d1adec11898b011f639a4dedc7bc6f03a875fcd89bbf46f9e791377d47c0e36691a8f1a60253b2d6f410afd0d0ab9d1619193954b2228541dd3aaad0ae69dde45da274f63f8495bd941614151e8eb930662c0bf1f62a58a7edbe9cf50828d76e71fd4d7798c68ca40a42a4a7dce965878638eda7b208dcb72a994a03a6b4704a99218ccf0fa05a6bc2db0d41acad23e40ed9aa231a6df0f4b31c8bf7567a03dc714eb38af6acad9d9301b679b66e1460bf3a9814ee4fec3b049bb335f8ca4858daed76db836de1ee971f4184222d7a0013a30d880a152d656ac49e48b2bb0261fac547125f32a9b8bfdb4e69d246c1675df7cc2bf273aaa8db0631bcf4626e3b5e778eb57e092c86b5e42dd39e6f5bfb00a78fbf1c28202f1b3589abdea1bd0061b6794738bd6afc96799784d8f8dba443ee328082efbda26087175c14a3e26f6d000e8407c12588f81a1da6f000435518653c93aacf5f19554bdf071102faaa96d19443afdcd81eea5b5d5173d9a83eb37912c056c31bae2be155ec248d9c341d7590636b80faa3a0acd50a17571491f8ecfa280096fe761fdd7247d6911abbc3f98f0df3399a0828a2f2aa506137cf094ade594653867a2a6bcc8fe87d5c3aae2af810416b19eba14f916245efbb8e7287f1fa9dc78b8fb90fdc62724ec85a2d5609456f16ea2f2b1ce14f1b07d3f7a26a7493864f91d665cdfed147867e06e700aad923e5baca62a70d232c4988f32ffb0ca6f29c43d3e4d8a654d353f06cbbe176008158fd0ea3d9ef2df04a648b5e4860418545d92308af8a2e2d81d49062ea3cc6fff15ee87f7071013ab2936de4ae5b377bab31042f62c64107ff07ddf1e057623978634237cf58f742486d71d67170edecb01d90f21fc8c5f0c2107a515534bb6999308c9757cb813e288300e596844b94b755800d82d672f74d11bb8c2974261d73a5a38e516bec3a28bbc148b632ee31c2b5bf1f28be9959e379884ab95fcb1ec57ffe92846dd5b1bd047eee698b94d1656d7e7a098fc3b3f47dd2f0f0cb71b6d708287c6c48628d805acd6ba1c0de25a288d3fd267490f54dfd393981e1fe26e72d4c7edbf5b0147ad9de95c91609520a6eb55cf1e7e422994d8b1714b0c11495a4cb04ddcb4b1db093bd3f9413297f66f0abcb804bbb0e6f6c547067e054c16bd3c8b583049153c6d01ff5a2d669fb2c7111d2c645f510f31c6143795ccd4cf3741d2bd7e1fb50024b129be48200c9281337de80b1e3f61de7b042c16629cf423bc2e2d925ef4627857de5bc787cd1a1f8b0a2fab8ccfbca02b1a29bc50853f6e7e11d57685f9a596e61d116542a9e6029f5b8c2b64211f1e0f899e35ad61a86c1f5c749257d53f6c09c04f35c7e1ebd015adddfddb2ae513530a707c1c215d1e305ae1a832aa5fa881bec403629a5b0c0adb7df103485d3d634d901347fdedf075e9d1b75b451d28a6b30912d84668374eab82f3ea329537909d047a74b27695631d2989c919a71349c8f954fce095d7956515532ff38cf8139fe4f8cf00dbeff65510aed8ef96fa9d15600a0d4b2c0f19fb48242db220d14a3aaaf66e07898fbc2f14ad39020d7c2da81b16ba337d874da014c367b933284f75199561eadcb847dc88d35acac2b6bc14a565b77be554dba8894287bff002b7a50eaa3c7fa47f6d3ad312deddfdcc9310e89b61a82c53aa7b436affeb6722a52ea88bc34f75fc4477625fac693e792ca57ee009aee5698a38d20b33b4bf46d4d028538c7adba49b0ee70c36a65c9bd6e7146c0946fe89acf641f531b83e07f1ea98aa78b74427d97f7638c106bfdfa8140810d509fb10801cd4f608929535cfe32c5ef469540086e3f0cc4d346b8e8947e6322fca4407ac201708f518fb3338e52e95f28b3b00d74f711d3a3efb158ba6a113bc058b07886dee809ca0855363d22f4339af23c03f7ac7706a6743bf9858d8ef4aabed8a8f558e8b14f9749cf9a697227506eeb4d0b8c8ac0d52acb8dd175e1bb580cdfcb5001a6551a6759eb9d509e222fad74e33e9c4b58b82933463b5f9273f3780fec7d4d9ab7ec4f812534eca1fcb71612e06aff1e295e1f9369f3cf96e0e1dc6711ea24cb599508cf22c54d933f6877a00327becf64178bd736fca118e74bade6aae8b8b1a37da13ae3f46507bb0b8e7cb3a9bc7dbb80f7faa6d2d11a82e7e9e01a39130828dc13cabc217bc232f1b8369ec3ce18a4de38c99b5eaa083f8768fa17ab946d194426014e76e088aa991a54273bff43c7732be0b80ce203b9f428a0e27f91e83a9eed8b5deece81b57988e1c0a7934511ee897ac040e9da8a7db471efb8fcac0d606f8b5fdc84dc73871e78a2f1ee98633aee82d44ec5dab4cc34f68b2aacc26a33357a5cee774f11cf5fa38152489cb5bd443f75aa030f3b834f725d0c6419bd4f9283fa09abb985506b1f6b4d151dc86bedd8c09cfbb961e25d4fb02ea1b0ad19ad8816f284235f37e0a0f58dddfb7a0c3217d6915ffc88c5ab475e8ac06ac63e922930240f0b1b75784f01e41a83113091408961fe1b4b00e9842a91f4cbc1803d182656b4cdf113e5855e046f46a9097d1a3ba8318ed196ca8e68b1a48d057ab1e33ceb4db8953a2c3aad1b7df2900b3103173d2138eeb0f5500ab197aabbf09dae4df3a511f9abeb3134c23fb8a7cd90682e566d498cb64e50624b9f55e9d3761257e3512f621f5e782ece59d4479cedf04952497f8920fe889f5ad5f993b902b834e95c570603436ba50bdf2c4d4dc8c08ae221a0f72aeeaf5f0c81cf6da2cbbd6e57af26a094c8e742172adc55ba23d2924fca3db40ef061971055fd85b2e360e6b3c30fb786853e8b0eed2dea162561d605c5bb4376ab808486bac374144bcd4eb67ba30f2404a0369762e59ccda24a1b466c35a0445f3bc743d000402ee6078db2a6bb8b2a789558a3a86f8be2f5ca3a2e0847391ef8f812ae2e96bf4cbe1e9acea1c24f4d776ee6e7590d7aca6a35a0e408cb67949b79c1e8def2677560cb9cf24f60a2db6ea273f13a53000bedb422061443c2239b2665a7af7a58505b981e2d411ed19bb522f21dc75e8a8ba82834faf20ec012daa886aa628f4ef31545fba78e7cf7daf67d2f64b98e2f31042e6fce9c0819508c0da259087521e4fd9dc1797e976ea538ea4f957ce1643dd30b45def215b84af9ec3c53f8f52774b089d75c7d79f2eb45b29cc66f9e48a5a89f7521435bbbe915961a018e98fa61a3bbed74f1f7ca15ceb858cc650a7b2fa3673083e7f2008c253c143a5891189eea45b137b87e256f0c1ab9d409340f10d4b2b0da3c35e8c3fe25554f7ed71819842aed43f900198c710c072a5304b1fabea3d922142a7bd1a3fcdbe60de08301f800295830c292d0b81824613a771af7115ef25ae2c8d55307f8f6de371ced08d102df079af8f9cc3104d5c1c5c39e91022d77fa0a543c5a1b25ca5e4d52b05cf36010f56362a1df5a0f54dff3e215b3fcc24dc6ac8c37e1b975af26d8710cde4969daea2d46dcc61acfbdcd937684de70b339b936eb97cfaee39ead33e9ae46fc26be322e87113eff536f0480c2ed331388b253fb2d225a958ab312a6d6df3b500181e3530b320cb3c7238d76d811aff3d3f3253239356320b5d90f39c969a75b49a8f5ee7b86b4bf81b41c05d3f71c9aeae52e9df7381e8b8e3cf32a3b65cd088b946f9149c6e40e39528b4a9ee9d2acd2c68bbe714c8470c3a5e0f68a0d954965bc475258b3485c185184b1179361c3c6bcbf23c6c9dad172f4a33fed73b8f6a5fab691cd300d06587ed6ebeb82786f45878f835a8e3f32bd80147d1a64b79fe0cdb5318f6bf141cb2d99e9eb8d1cae18563f5c470df2e7d5578f2d2b8eb49b2e904af52461c7606b485fbc400e5a37c9aba35f38624940a738277b32ce71bb165ea4e42caefed746852ed936dd493c034ab42d631ab020b051a5608bc85df26f6fee5a66d28cc3c579b17c5a12d159a72bcee7b2401abda9b682bcb44f1083efce36f801b1a6eba5deb0d91163b58b8d0b5cd2d9a8b9629771b0e1b1d5b877e05627945e63e108313512f29991eb23bacb05b9bd7ac144d674bc1fb616604b39e08229849fd780718f7295c204ad4fd480c5dd803b5bd4671fa4152750a1d4474c90e8c191112be33dc81c3499082be407a57692ae4e5ee0b40a18d357c3d16e9e29f2abc0ea546b74bf16ee1a0388522a205d575d8a81afdb0c98c24c2e24941c6fdf9fa6aa3dbe7f8223e1d0a9c7fdd3f3e9dfdcf83057e66d1995a7f839fa8573abfdf81c621b846ae1ae49738fed6d78d6d39148f19624fb7b2fb97b9ace24d053bb71fce43ac63faf0f9eee3f8ff04b759b8a3d426976d25b1724686d9db4052c0facb00827bcd6c0e3dbb373abacb4b29cd9ac23b09105e162156a295f1fd202d2bf1ba7b2642c0f1cb91fa4a092cf798629edea077d426ffde989bd891d06927c8d86920a02ca15ad5ac2d96b94c3d55c83aa5416e506c91a73dab9593a0471322f773e0500b39871468ce7914d4cc07ca36b18915f66ee2e21f91189d61b59209e0f160522cdb45843c18bef3f826d2015185eac75e1873a1be3955f34ddd41fa3f64be60e2f6c506cd537978b59273f76f790585cdfb627e0725c5ed600d185e0c0c2cc23b7c61ec6d8b9d46ed857174ba572e96f84db38247e5112d87a478c834bba5fb44eada9cfd1d8f8df6fd484bc6b3573fd60bac76e22f70df1439bf4a2f735e86079c7a2ce1ad7e1673cd139d1095ba5c91172bc920ef42497f490ec3d0db4387687a43aa9201e551f4db6f48a39a6c46f026d9d39ff4a9437889f64e98d879ec103b8e8202f739d3d863a1e8fe8a4f6b83c13ea3133c0ac9ecf3198a893facc01c4554dd489276ac2cd691d8ef731ff81e928bf379d5b50c7bcd3ad14ae39f8cf57b195a9da9405d7188227a12223df52b5448d624ef6a5d4ed214a90ccddb2d90dc0e111740cb6f79cfff2ca85df190f9b9ead308d2cb440488c20c2a897aca2eee4dd70e8419c07035a734cd9c36a972f605702f76f90a32df992e49def3d03f6ca192401341cfdd01c049659ab3ee6bb83499325eb2a90487c1423ae94a9a64d544f9924e3a278747ba715a47b301031e425c6c95d90a44b2deebc90a495bad1561f0e3a8b1291c632a17300739d99ee332cc7ae58d23ae04ab618dd24d14a2d316842d340a08304b7c8c146b3b9ecb0f140949bda1d9a7c6ff7de116145b45df340ad28bbd1d3bee38a890b3f0477b802cf7f558b05eae5f4830575e7e9824fdf2e8075f1ffe56dfd141b6fccca72ea0220cb85d4e697e541c83719f902eff1dff78cf35dda7fe1fc2ae2b21e3d798bbbef04cfe8d2f6c295c2d1084a0a4535aeb7289422b3cc855748202d06b75c5e60afb48545070895e87296afcaf477dd250b4257a558a30a3e855e132d551f873dae38cb0acd67dd861a352260adbb28fc5bafb4ffe3c082d0e182bef47a2b02ff01310fb05f827a2277c5604200d580614f69f01d5db8384307c157a206a797a1d19bfa515cf532fbe5fd7c87db1ff0e525dac34210f30cfaa6459a10f00c25acd4a28052d9d46d706e622ee94fb3f5e46e76aa5bfb32d54e1b6b84d068acc8e53e0cc8bd2a89febbea522741612af4f658bb48a793a5d545153f8fd55c8914f5800728f1c5753eef56369d9e3cf67fe88bed268f725bc4bcad7b89e6eee3c0c5a2ec58e4b7245351a1f4dbf5188b41c9f22f481668ed485aaf10d8ad5896a0358dce6a2b96c73cd3ddf8dbb60c8ce37c7fc0af385adbd5ab533875137f513cad71239e9cdb6dee0f577612efce1cffccc465e7edcdbcd71d7b577bf8d46da8ac1d86d6d61113837d2fffec824e07a283d7c190ed67dd3b4350058247c5b5a707e8ad9b4c6fa3ca0107b8e719e9ab2c0dc398fcab8f31cf9bf95fc8363f4db815e2b73ad731c8ea89b7b1cba5b81aadef440bf2657e442def16b909adac973e82f127276cd7dc6b69511b26e18849a7334e70e0ea66c7341ba3d6546dc02d4942c5ea10de4ab5e24849fc291519a733e53e3a6831c6808ba5f5a326641a3ff267bb85c2a92acc28f6ac135a747c16fca8d011c6d88269fec579557d5bcfa885c598fd026601bf4f09a6831c445ddb75918e0de92563e6dd4971cc61a4a0502a8538b7a77fa57c436e3d7bfdbb367256c56677a736a7551e67e1adc3759ac3dead45863d10b5b3bdcaf5400665a9c59c3b934f75956d99c24ea93ca870dd32a3ff5146e7b57f8b71d6e6fb54f62b3c59659afcd8b8b31d9847645a8c5a1a01a17f9a83df03e08a393de02409ee6968a3c282abeb265952169709f173fe8d1206fabaa0523a3671dc25ccc7fc1c77ce3c1d928d00b8b8fbc29eb0043b4fee717ee7373a0abc281124cc69b143a48a42570b39abde5fbfce037823c0d93dc91126f67932ef2a80b2f44b729e28fc4bff7baeb77ef842274fe921ddf0203c1c9b531bf6ccbc997197964bb12d376482f717fd5e3acc79c0855aa7214e92d1eed4603935c52c99f2721d021802d0efb6a9b6cbe5a3e73c8b21120e6fa3bb421b8ff572d16e7285edcf80b01918e121fc93de4b087978effe9a37f4f3b85a2aab1abc4c4299d68304d73a9672da6226f7b78284a33040d51d75cee44ab5f5855ba9a16b6ae9ff602a0a4a764ed67aec547f7d11353d17ade0bb7be930149f4635fb9afe9eb6aa8153f32bea57e0422c372ee8bce31d23f267d3c168b72a8d22ee31c30a1d68d67259846af6c301832d057308fb093fb859664cec8ebbb3d492c9d5a9c4da5f5f5900004369dcb6202ab78e8ef270369900d177dd6d873d89b7998e569dd45a8b1acdada969ff1c39261f3aa64ef6b99ecd8b2eaaf2164c34b47d1da6aed75095f2912c0cf07fe39b9cf0f0e3a7ec2f107e532f39f396eb04ab0b6739a9d87ffdb093d4b4fd10edd29e40ca688f3958594d1d697d4bd536a2068507cede6163bf4d953223c868a57df9e72a3088f8fda429715f6e93313e4e6d7179919652410a46cdefd3e7dd0c9289e132a260a2e98b7d0b93c5776a0843df7c22cc2e0459022ae06f1972ed0d93db96ff35d79b2767da919f01feef5ed7772ba613e189429d93f9fc8d09d18aa772aa1fdc4df2ff60e3a83f524f9f4733ebcf1f2130397156a1fd7ba16413322969a7ab1e51bc33e5c74396945bb33d43aecb67c0c76630f3fdafddeea0d84e748bd9e9a542bfd1ffd23b64e28df17057aa2c1421ea2c39d439e651919ceb5291421082dc5c046fd3c09d619c4630fa0e07f3e8d56c86043e05c2e7f51a67322c861f6ae718c9c4698dd2869c959f2709432fa0847ff9777ca2939553a630f30eb848e5962777d1e88d038dafbb4e6b2dbbd89eb9b110a53dda33a30d515d2dee1aa14d925877cf7f01c9d1c22e791175bc8885383825a5e4b7573352858f99a54756776782cd71790fd0e5ddacee0f18b9496e41b822676543e5e0f38b59bffa0605818643981c60bdbba22b487dc5d0ab8491849fafcad3a0c988432163857416110a662e5accc84fe6f12047d836513ea5114484f556b1c93f59a119544cf3f20e6bf0204efbee281107dc28fcf897eb4eb254a0e78fef7b8e81804be91559fabacdc86a9993c2a28443a55938e7e996f9905b3e361035287c7653539f1c5ee2a3b4f9497d8132f44aa0cd9cb30309dcb113c5ea0569d0bba99632e9cd25245c734ee958b008b47683eaa2aff12be5f47803c2a539ad1cc195badd9da86409cff0d86e81f999fdcff984fe479d5f69798d7abc9a773aaf56af1049453289359c1ea477ba7827c97f9c9c138eaf05e2997128a0375831ca37645275a94b5baab867a63446753f3be5fe7d116dc72cf64be0d5efe20337c5e0ceee9b59b516763be57efe2ace1375448cbde85f2ef9dd483acda5d2456c4934dd6ff40790e1323fd51d9fa3ffc0c699392fe63e9ac115829c8411b8efb96b21b4a8b97a04b6c5ea5e51d49a925605953da1e169f80ba980e8f3e6e56688f09febd6ea8e3ccd9fc09030224a0026adf0f27ca1e6bdc793f0f7947a3f2f3e44576fafb8a87e18439b2c1e641d2ad269dd19ae2b67aedb3c0be79e121f59f4ce641e731c0bea50d667ede69f8182b315887af8ed68656b059c36964acf7afc7abcb2d820688b5897079b94d58cdaf452a86960bf89d7d27675e5e9f8bbe890a7c7a03b91a3fbc803528812beb4e5c37a043073a26aed42849a9df1fb0e499e3509421bd2cf23a9089004083c0013555881efc47b79d78d185bf61f04d83d5b00dce1977ffefc2e1ea9b95f429e7ad4bb04925c610aea04ae1cc1736c02b666f342f86dfc0e00f0f9635aadd2d89431f4a0cc2c1fd3574dd184818c31fb1b58d584e8f1ddbfcf39a0c9aefc3e850c702e33624988042d196b03afa05356ecacd552bb05cab73f65ae1c0fc545808f25489ca591848e814195e372aba635452fbd975d71127fb3e3e4f2f4220f9fc70e945305f257bcee6cfca9a11a6a594327c37ad684adac5f3e3ed2ef527145ec4a777b9348470ad1a71627d53f35af919e3db971b14b4807f5fe28bac2a8abb285d1f377f5e7b665b576f49f687a164ba094c7f50e2e03daa7e2a5bc9e75d78e8f0d03f5204eed634f64cf1cf10bf7a35c3ddfb66f63a8b66594fab2799f2a4c07baf04fa76f4729bcb742794d1fc2d1d8915589c6c7570e3f721ad6c34c98ab0126b18d99837902121532f2416b6b35ec34510996330efcc4a1f79a759d3fa08469968b450948c1e5b05f83be97921a9366d995a3d6140ceecd407dc102427f8edaf91f781d1ec60463f9a3bc061179b64310073ec2ac3d8a92cfd197f653535b01117961f31682ba56e6cfa9150110fbcd2ac21811476b3f6153d72ccc94242d8e39ebe9cfcf13a9e99584eedc91a5fbe10de72dfb18fb84362ff33fea7528d8bb796d313e5cb565525ca856d734f8dad6daeb56078952b6675715782f56bec9d47c9365cc871b56535e4c6fe57e05f731715fbd9c51f0135cddd11a2474c631bded31a1eb364d32e817475df8bc4238076654c1adfc3bb2e088370f829a77e66d183a39d93ef50bce709fb286abbc822a946172088b9cfd1685d4f41e0d1c2c5759c877e6689e2c05afb1051d2b6a7d77ef579334cb1786a534acf712164d363f1b58e40c01e419b22838d822e1e61a0f2138f05d0acc4f74564612e6ee2de360ae5b340d8fb9d9b96ccef756b4518bc7744f61fecd18220f41d6e2005a834910120a739a4836fa5e68348fabfd39b6ef042da6511fe1c5981ec40b090478594d6fe4e4ce2a021d166da528a1ec656621513dd8e65318891e53f9a82371475ba6846c0480697cb8ad2b963af2286d15b54e71df723a6cbb0bbfcd947e25748679c63146932cebaadc66062509016924be03ffc634e996506817de7cd2e5080ccfd4236cd6cabb81d419396bd71423214f2fb0d287148ea1515cd766569b2eb37142e71194e795059a8321c0a51bcc5ff3d4852a7b43310fa0dcf473cc43f4afea1dfbdc979e4e22cf033c90557508a89393a82e14ddac148bd2cd95675f0eb54c19a4fe7b4862d59fc1d91a130d8f2a9618ca9c537c85fc6601733df47c4bae029e54edfc862299fbbababc317f2e32e13ea2f6fcbdc5594fc98877b07f019cf49661679f8982bb828b71e8d9d0dd0ea3f203509895969c5f771d9a906f07e358aafda5a83ffb2a8ff1514221fef5442c58d6ee4a2dd5015993e68fe58dc99ab22e5e882c7adb349baeb2fb53cb59c3fe60ea6eaa7953e37d2739378210b766674c82c0213d7d5d86b04216b097e05d356e128d51154a274aa07bc623c2056aefdabafc7493ee79c1edc62b3e6329c777679359c74942e62ba61342a9e9a14090e974ce16345ea7235d6b3895dd2e2e5321796b46c6a2c0eb0c155e8e35d8e344954f86023ee26036a118fb67a575ab877def7939b23c1011b6177ec58559ead6cc217f0a0169397bf98ab7060ea31a50359cf8197f95238a98559aacd217a1328533378b1fbcb9b5be39c0512f98629c5c7f8b817c9e429e2ca406283c056c9e0ded43df38a7c55c8b14aa05c52de4065a7f4538d8cb5cd95563d9a52c98c792dde5727d8705346a5ee9eecf314c06cdede200b5ed743c9b93f9271c86256d03ecc75f5690cf0245b3831a9d91cbe352bd35ff95a18f5a54b807f98430a19908ee47eb6332aa545a415fbc18394aab4dcf120a3c4bcc72c0cfd776f39447800f7c17ed423294e8e23290807c91efa0944e3c5fe64d7d8fd02defc26d30c1dcf98a7d52f13948de1d583cfbe5bbe903ad107a0d61429276e7f8889a1f1f25c7832530b7e290972936a3691d944804dcc6614b6f0428c2a9b3e752a03ed5d6c2d55dcb0d06a42311d77790ba351eaab397447f5ce13c6b1b4e9c59a2ac5d63edfd48f65090b5a6dababf5c2d28a11236df9d3df92fbbb4b0d03f0abd154afd4aaca1e48e07f8037580d6287b0acdb7cc5817ab4ae4ba6484199f81d481698c1b297","isRememberEnabled":true,"rememberDurationInDays":0,"staticryptSaltUniqueVariableName":"e58622878c5b4107a5c053c29b821537"};
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
