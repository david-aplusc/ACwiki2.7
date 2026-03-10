<!DOCTYPE html>
<html class="staticrypt-html">
    <head>
        <meta charset="utf-8" />
        <title>Protected Page</title>
        <meta name="viewport" content="width=device-width, initial-scale=1" />

        <!-- do not cache this page -->
        <meta http-equiv="cache-control" content="max-age=0" />
        <meta http-equiv="cache-control" content="no-cache" />
        <meta http-equiv="expires" content="0" />
        <meta http-equiv="expires" content="Tue, 01 Jan 1980 1:00:00 GMT" />
        <meta http-equiv="pragma" content="no-cache" />

        <style>
            .staticrypt-hr {
                margin-top: 20px;
                margin-bottom: 20px;
                border: 0;
                border-top: 1px solid #eee;
            }

            .staticrypt-page {
                width: 360px;
                padding: 8% 0 0;
                margin: auto;
                box-sizing: border-box;
            }

            .staticrypt-form {
                position: relative;
                z-index: 1;
                background: #ffffff;
                max-width: 360px;
                margin: 0 auto 100px;
                padding: 45px;
                text-align: center;
                box-shadow: 0 0 20px 0 rgba(0, 0, 0, 0.2), 0 5px 5px 0 rgba(0, 0, 0, 0.24);
            }

            .staticrypt-form input[type="password"],
            input[type="text"] {
                background: inherit;
                border: 0;
                box-sizing: border-box; /* This ensures padding is included in the total width */
                font-size: 14px;
                outline: 0;
                padding: 15px 30px 15px 15px; /* Adjust the padding to ensure there is space for the icon */
                width: 100%;
            }

            .staticrypt-password-container {
                position: relative;
                outline: 0;
                background: #f2f2f2;
                width: 100%;
                border: 0;
                margin: 0 0 15px;
                box-sizing: border-box;
            }

            .staticrypt-toggle-password-visibility {
                cursor: pointer;
                height: 20px;
                opacity: 60%;
                padding: 13px;
                position: absolute;
                right: 0;
                top: 50%;
                transform: translateY(-50%);
                width: 20px;
            }

            .staticrypt-form .staticrypt-decrypt-button {
                text-transform: uppercase;
                outline: 0;
                background: #4CAF50;
                width: 100%;
                border: 0;
                padding: 15px;
                color: #ffffff;
                font-size: 14px;
                cursor: pointer;
            }

            .staticrypt-form .staticrypt-decrypt-button:hover,
            .staticrypt-form .staticrypt-decrypt-button:active,
            .staticrypt-form .staticrypt-decrypt-button:focus {
                background: #4CAF50;
                filter: brightness(92%);
            }

            .staticrypt-html {
                height: 100%;
            }

            .staticrypt-body {
                height: 100%;
                margin: 0;
            }

            .staticrypt-content {
                height: 100%;
                margin-bottom: 1em;
                background: #76B852;
                font-family: "Arial", sans-serif;
                -webkit-font-smoothing: antialiased;
                -moz-osx-font-smoothing: grayscale;
            }

            .staticrypt-instructions {
                margin-top: -1em;
                margin-bottom: 1em;
            }

            .staticrypt-title {
                font-size: 1.5em;
            }

            label.staticrypt-remember {
                display: flex;
                align-items: center;
                margin-bottom: 1em;
            }

            .staticrypt-remember input[type="checkbox"] {
                transform: scale(1.5);
                margin-right: 1em;
            }

            .hidden {
                display: none !important;
            }

            .staticrypt-spinner-container {
                height: 100%;
                display: flex;
                align-items: center;
                justify-content: center;
            }

            .staticrypt-spinner {
                display: inline-block;
                width: 2rem;
                height: 2rem;
                vertical-align: text-bottom;
                border: 0.25em solid gray;
                border-right-color: transparent;
                border-radius: 50%;
                -webkit-animation: spinner-border 0.75s linear infinite;
                animation: spinner-border 0.75s linear infinite;
                animation-duration: 0.75s;
                animation-timing-function: linear;
                animation-delay: 0s;
                animation-iteration-count: infinite;
                animation-direction: normal;
                animation-fill-mode: none;
                animation-play-state: running;
                animation-name: spinner-border;
            }

            @keyframes spinner-border {
                100% {
                    transform: rotate(360deg);
                }
            }

            @media screen and (-webkit-min-device-pixel-ratio: 0) {
                .staticrypt-form input[type="password"],
                input[type="text"] {
                    font-size: 16px;
                }
            }
        </style>
    </head>

    <body class="staticrypt-body">
        <div id="staticrypt_loading" class="staticrypt-spinner-container">
            <div class="staticrypt-spinner"></div>
        </div>

        <div id="staticrypt_content" class="staticrypt-content hidden">
            <div class="staticrypt-page">
                <div class="staticrypt-form">
                    <div class="staticrypt-instructions">
                        <p class="staticrypt-title">Protected Page</p>
                        <p></p>
                    </div>

                    <hr class="staticrypt-hr" />

                    <form id="staticrypt-form" action="#" method="post">
                        <div class="staticrypt-password-container">
                            <input
                                id="staticrypt-password"
                                type="password"
                                name="password"
                                placeholder="Password"
                                autofocus
                            />

                            <img
                                class="staticrypt-toggle-password-visibility"
                                alt="template_toggle_show"
                                title="template_toggle_show"
                                src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCA2NDAgNTEyIj48IS0tIUZvbnQgQXdlc29tZSBGcmVlIDYuNS4yIGJ5IEBmb250YXdlc29tZSAtIGh0dHBzOi8vZm9udGF3ZXNvbWUuY29tIExpY2Vuc2UgLSBodHRwczovL2ZvbnRhd2Vzb21lLmNvbS9saWNlbnNlL2ZyZWUgQ29weXJpZ2h0IDIwMjQgRm9udGljb25zLCBJbmMuLS0+PHBhdGggZD0iTTM4LjggNS4xQzI4LjQtMy4xIDEzLjMtMS4yIDUuMSA5LjJTLTEuMiAzNC43IDkuMiA0Mi45bDU5MiA0NjRjMTAuNCA4LjIgMjUuNSA2LjMgMzMuNy00LjFzNi4zLTI1LjUtNC4xLTMzLjdMNTI1LjYgMzg2LjdjMzkuNi00MC42IDY2LjQtODYuMSA3OS45LTExOC40YzMuMy03LjkgMy4zLTE2LjcgMC0yNC42Yy0xNC45LTM1LjctNDYuMi04Ny43LTkzLTEzMS4xQzQ2NS41IDY4LjggNDAwLjggMzIgMzIwIDMyYy02OC4yIDAtMTI1IDI2LjMtMTY5LjMgNjAuOEwzOC44IDUuMXpNMjIzLjEgMTQ5LjVDMjQ4LjYgMTI2LjIgMjgyLjcgMTEyIDMyMCAxMTJjNzkuNSAwIDE0NCA2NC41IDE0NCAxNDRjMCAyNC45LTYuMyA0OC4zLTE3LjQgNjguN0w0MDggMjk0LjVjOC40LTE5LjMgMTAuNi00MS40IDQuOC02My4zYy0xMS4xLTQxLjUtNDcuOC02OS40LTg4LjYtNzEuMWMtNS44LS4yLTkuMiA2LjEtNy40IDExLjdjMi4xIDYuNCAzLjMgMTMuMiAzLjMgMjAuM2MwIDEwLjItMi40IDE5LjgtNi42IDI4LjNsLTkwLjMtNzAuOHpNMzczIDM4OS45Yy0xNi40IDYuNS0zNC4zIDEwLjEtNTMgMTAuMWMtNzkuNSAwLTE0NC02NC41LTE0NC0xNDRjMC02LjkgLjUtMTMuNiAxLjQtMjAuMkw4My4xIDE2MS41QzYwLjMgMTkxLjIgNDQgMjIwLjggMzQuNSAyNDMuN2MtMy4zIDcuOS0zLjMgMTYuNyAwIDI0LjZjMTQuOSAzNS43IDQ2LjIgODcuNyA5MyAxMzEuMUMxNzQuNSA0NDMuMiAyMzkuMiA0ODAgMzIwIDQ4MGM0Ny44IDAgODkuOS0xMi45IDEyNi4yLTMyLjVMMzczIDM4OS45eiIvPjwvc3ZnPg=="
                            />
                        </div>

                        <label id="staticrypt-remember-label" class="staticrypt-remember hidden">
                            <input id="staticrypt-remember" type="checkbox" name="remember" />
                            Remember me
                        </label>

                        <input type="submit" class="staticrypt-decrypt-button" value="DECRYPT" />
                    </form>
                </div>
            </div>
        </div>

        <script>
            // these variables will be filled when generating the file - the template format is 'variable_name'
            const staticryptInitiator = 
            ((function(){
  const exports = {};
  const cryptoEngine = ((function(){
  const exports = {};
  const { subtle } = crypto;

const IV_BITS = 16 * 8;
const HEX_BITS = 4;
const ENCRYPTION_ALGO = "AES-CBC";

/**
 * Translates between utf8 encoded hexadecimal strings
 * and Uint8Array bytes.
 */
const HexEncoder = {
    /**
     * hex string -> bytes
     * @param {string} hexString
     * @returns {Uint8Array}
     */
    parse: function (hexString) {
        if (hexString.length % 2 !== 0) throw "Invalid hexString";
        const arrayBuffer = new Uint8Array(hexString.length / 2);

        for (let i = 0; i < hexString.length; i += 2) {
            const byteValue = parseInt(hexString.substring(i, i + 2), 16);
            if (isNaN(byteValue)) {
                throw "Invalid hexString";
            }
            arrayBuffer[i / 2] = byteValue;
        }
        return arrayBuffer;
    },

    /**
     * bytes -> hex string
     * @param {Uint8Array} bytes
     * @returns {string}
     */
    stringify: function (bytes) {
        const hexBytes = [];

        for (let i = 0; i < bytes.length; ++i) {
            let byteString = bytes[i].toString(16);
            if (byteString.length < 2) {
                byteString = "0" + byteString;
            }
            hexBytes.push(byteString);
        }
        return hexBytes.join("");
    },
};

/**
 * Translates between utf8 strings and Uint8Array bytes.
 */
const UTF8Encoder = {
    parse: function (str) {
        return new TextEncoder().encode(str);
    },

    stringify: function (bytes) {
        return new TextDecoder().decode(bytes);
    },
};

/**
 * Salt and encrypt a msg with a password.
 */
async function encrypt(msg, hashedPassword) {
    // Must be 16 bytes, unpredictable, and preferably cryptographically random. However, it need not be secret.
    // https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto/encrypt#parameters
    const iv = crypto.getRandomValues(new Uint8Array(IV_BITS / 8));

    const key = await subtle.importKey("raw", HexEncoder.parse(hashedPassword), ENCRYPTION_ALGO, false, ["encrypt"]);

    const encrypted = await subtle.encrypt(
        {
            name: ENCRYPTION_ALGO,
            iv: iv,
        },
        key,
        UTF8Encoder.parse(msg)
    );

    // iv will be 32 hex characters, we prepend it to the ciphertext for use in decryption
    return HexEncoder.stringify(iv) + HexEncoder.stringify(new Uint8Array(encrypted));
}
exports.encrypt = encrypt;

/**
 * Decrypt a salted msg using a password.
 *
 * @param {string} encryptedMsg
 * @param {string} hashedPassword
 * @returns {Promise<string>}
 */
async function decrypt(encryptedMsg, hashedPassword) {
    const ivLength = IV_BITS / HEX_BITS;
    const iv = HexEncoder.parse(encryptedMsg.substring(0, ivLength));
    const encrypted = encryptedMsg.substring(ivLength);

    const key = await subtle.importKey("raw", HexEncoder.parse(hashedPassword), ENCRYPTION_ALGO, false, ["decrypt"]);

    const outBuffer = await subtle.decrypt(
        {
            name: ENCRYPTION_ALGO,
            iv: iv,
        },
        key,
        HexEncoder.parse(encrypted)
    );

    return UTF8Encoder.stringify(new Uint8Array(outBuffer));
}
exports.decrypt = decrypt;

/**
 * Salt and hash the password so it can be stored in localStorage without opening a password reuse vulnerability.
 *
 * @param {string} password
 * @param {string} salt
 * @returns {Promise<string>}
 */
async function hashPassword(password, salt) {
    // we hash the password in multiple steps, each adding more iterations. This is because we used to allow less
    // iterations, so for backward compatibility reasons, we need to support going from that to more iterations.
    let hashedPassword = await hashLegacyRound(password, salt);

    hashedPassword = await hashSecondRound(hashedPassword, salt);

    return hashThirdRound(hashedPassword, salt);
}
exports.hashPassword = hashPassword;

/**
 * This hashes the password with 1k iterations. This is a low number, we need this function to support backwards
 * compatibility.
 *
 * @param {string} password
 * @param {string} salt
 * @returns {Promise<string>}
 */
function hashLegacyRound(password, salt) {
    return pbkdf2(password, salt, 1000, "SHA-1");
}
exports.hashLegacyRound = hashLegacyRound;

/**
 * Add a second round of iterations. This is because we used to use 1k, so for backwards compatibility with
 * remember-me/autodecrypt links, we need to support going from that to more iterations.
 *
 * @param hashedPassword
 * @param salt
 * @returns {Promise<string>}
 */
function hashSecondRound(hashedPassword, salt) {
    return pbkdf2(hashedPassword, salt, 14000, "SHA-256");
}
exports.hashSecondRound = hashSecondRound;

/**
 * Add a third round of iterations to bring total number to 600k. This is because we used to use 1k, then 15k, so for
 * backwards compatibility with remember-me/autodecrypt links, we need to support going from that to more iterations.
 *
 * @param hashedPassword
 * @param salt
 * @returns {Promise<string>}
 */
function hashThirdRound(hashedPassword, salt) {
    return pbkdf2(hashedPassword, salt, 585000, "SHA-256");
}
exports.hashThirdRound = hashThirdRound;

/**
 * Salt and hash the password so it can be stored in localStorage without opening a password reuse vulnerability.
 *
 * @param {string} password
 * @param {string} salt
 * @param {int} iterations
 * @param {string} hashAlgorithm
 * @returns {Promise<string>}
 */
async function pbkdf2(password, salt, iterations, hashAlgorithm) {
    const key = await subtle.importKey("raw", UTF8Encoder.parse(password), "PBKDF2", false, ["deriveBits"]);

    const keyBytes = await subtle.deriveBits(
        {
            name: "PBKDF2",
            hash: hashAlgorithm,
            iterations,
            salt: UTF8Encoder.parse(salt),
        },
        key,
        256
    );

    return HexEncoder.stringify(new Uint8Array(keyBytes));
}

function generateRandomSalt() {
    const bytes = crypto.getRandomValues(new Uint8Array(128 / 8));

    return HexEncoder.stringify(new Uint8Array(bytes));
}
exports.generateRandomSalt = generateRandomSalt;

async function signMessage(hashedPassword, message) {
    const key = await subtle.importKey(
        "raw",
        HexEncoder.parse(hashedPassword),
        {
            name: "HMAC",
            hash: "SHA-256",
        },
        false,
        ["sign"]
    );
    const signature = await subtle.sign("HMAC", key, UTF8Encoder.parse(message));

    return HexEncoder.stringify(new Uint8Array(signature));
}
exports.signMessage = signMessage;

function getRandomAlphanum() {
    const possibleCharacters = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789";

    let byteArray;
    let parsedInt;

    // Keep generating new random bytes until we get a value that falls
    // within a range that can be evenly divided by possibleCharacters.length
    do {
        byteArray = crypto.getRandomValues(new Uint8Array(1));
        // extract the lowest byte to get an int from 0 to 255 (probably unnecessary, since we're only generating 1 byte)
        parsedInt = byteArray[0] & 0xff;
    } while (parsedInt >= 256 - (256 % possibleCharacters.length));

    // Take the modulo of the parsed integer to get a random number between 0 and totalLength - 1
    const randomIndex = parsedInt % possibleCharacters.length;

    return possibleCharacters[randomIndex];
}

/**
 * Generate a random string of a given length.
 *
 * @param {int} length
 * @returns {string}
 */
function generateRandomString(length) {
    let randomString = "";

    for (let i = 0; i < length; i++) {
        randomString += getRandomAlphanum();
    }

    return randomString;
}
exports.generateRandomString = generateRandomString;

  return exports;
})());
const codec = ((function(){
  const exports = {};
  /**
 * Initialize the codec with the provided cryptoEngine - this return functions to encode and decode messages.
 *
 * @param cryptoEngine - the engine to use for encryption / decryption
 */
function init(cryptoEngine) {
    const exports = {};

    /**
     * Top-level function for encoding a message.
     * Includes password hashing, encryption, and signing.
     *
     * @param {string} msg
     * @param {string} password
     * @param {string} salt
     *
     * @returns {string} The encoded text
     */
    async function encode(msg, password, salt) {
        const hashedPassword = await cryptoEngine.hashPassword(password, salt);

        const encrypted = await cryptoEngine.encrypt(msg, hashedPassword);

        // we use the hashed password in the HMAC because this is effectively what will be used a password (so we can store
        // it in localStorage safely, we don't use the clear text password)
        const hmac = await cryptoEngine.signMessage(hashedPassword, encrypted);

        return hmac + encrypted;
    }
    exports.encode = encode;

    /**
     * Encode using a password that has already been hashed. This is useful to encode multiple messages in a row, that way
     * we don't need to hash the password multiple times.
     *
     * @param {string} msg
     * @param {string} hashedPassword
     *
     * @returns {string} The encoded text
     */
    async function encodeWithHashedPassword(msg, hashedPassword) {
        const encrypted = await cryptoEngine.encrypt(msg, hashedPassword);

        // we use the hashed password in the HMAC because this is effectively what will be used a password (so we can store
        // it in localStorage safely, we don't use the clear text password)
        const hmac = await cryptoEngine.signMessage(hashedPassword, encrypted);

        return hmac + encrypted;
    }
    exports.encodeWithHashedPassword = encodeWithHashedPassword;

    /**
     * Top-level function for decoding a message.
     * Includes signature check and decryption.
     *
     * @param {string} signedMsg
     * @param {string} hashedPassword
     * @param {string} salt
     * @param {int} backwardCompatibleAttempt
     * @param {string} originalPassword
     *
     * @returns {Object} {success: true, decoded: string} | {success: false, message: string}
     */
    async function decode(signedMsg, hashedPassword, salt, backwardCompatibleAttempt = 0, originalPassword = "") {
        const encryptedHMAC = signedMsg.substring(0, 64);
        const encryptedMsg = signedMsg.substring(64);
        const decryptedHMAC = await cryptoEngine.signMessage(hashedPassword, encryptedMsg);

        if (decryptedHMAC !== encryptedHMAC) {
            // we have been raising the number of iterations in the hashing algorithm multiple times, so to support the old
            // remember-me/autodecrypt links we need to try bringing the old hashes up to speed.
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

        return {
            success: true,
            decoded: await cryptoEngine.decrypt(encryptedMsg, hashedPassword),
        };
    }
    exports.decode = decode;

    return exports;
}
exports.init = init;

  return exports;
})());
const decode = codec.init(cryptoEngine).decode;

/**
 * Initialize the staticrypt module, that exposes functions callbable by the password_template.
 *
 * @param {{
 *  staticryptEncryptedMsgUniqueVariableName: string,
 *  isRememberEnabled: boolean,
 *  rememberDurationInDays: number,
 *  staticryptSaltUniqueVariableName: string,
 * }} staticryptConfig - object of data that is stored on the password_template at encryption time.
 *
 * @param {{
 *  rememberExpirationKey: string,
 *  rememberPassphraseKey: string,
 *  replaceHtmlCallback: function,
 *  clearLocalStorageCallback: function,
 * }} templateConfig - object of data that can be configured by a custom password_template.
 */
function init(staticryptConfig, templateConfig) {
    const exports = {};

    /**
     * Decrypt our encrypted page, replace the whole HTML.
     *
     * @param {string} hashedPassword
     * @returns {Promise<boolean>}
     */
    async function decryptAndReplaceHtml(hashedPassword) {
        const { staticryptEncryptedMsgUniqueVariableName, staticryptSaltUniqueVariableName } = staticryptConfig;
        const { replaceHtmlCallback } = templateConfig;

        const result = await decode(
            staticryptEncryptedMsgUniqueVariableName,
            hashedPassword,
            staticryptSaltUniqueVariableName
        );
        if (!result.success) {
            return false;
        }
        const plainHTML = result.decoded;

        // if the user configured a callback call it, otherwise just replace the whole HTML
        if (typeof replaceHtmlCallback === "function") {
            replaceHtmlCallback(plainHTML);
        } else {
            document.write(plainHTML);
            document.close();
        }

        return true;
    }

    /**
     * Attempt to decrypt the page and replace the whole HTML.
     *
     * @param {string} password
     * @param {boolean} isRememberChecked
     *
     * @returns {Promise<{isSuccessful: boolean, hashedPassword?: string}>} - we return an object, so that if we want to
     *   expose more information in the future we can do it without breaking the password_template
     */
    async function handleDecryptionOfPage(password, isRememberChecked) {
        const { staticryptSaltUniqueVariableName } = staticryptConfig;

        // decrypt and replace the whole page
        const hashedPassword = await cryptoEngine.hashPassword(password, staticryptSaltUniqueVariableName);
        return handleDecryptionOfPageFromHash(hashedPassword, isRememberChecked);
    }
    exports.handleDecryptionOfPage = handleDecryptionOfPage;

    async function handleDecryptionOfPageFromHash(hashedPassword, isRememberChecked) {
        const { isRememberEnabled, rememberDurationInDays } = staticryptConfig;
        const { rememberExpirationKey, rememberPassphraseKey } = templateConfig;

        const isDecryptionSuccessful = await decryptAndReplaceHtml(hashedPassword);

        if (!isDecryptionSuccessful) {
            return {
                isSuccessful: false,
                hashedPassword,
            };
        }

        // remember the hashedPassword and set its expiration if necessary
        if (isRememberEnabled && isRememberChecked) {
            window.localStorage.setItem(rememberPassphraseKey, hashedPassword);

            // set the expiration if the duration isn't 0 (meaning no expiration)
            if (rememberDurationInDays > 0) {
                window.localStorage.setItem(
                    rememberExpirationKey,
                    (new Date().getTime() + rememberDurationInDays * 24 * 60 * 60 * 1000).toString()
                );
            }
        }

        return {
            isSuccessful: true,
            hashedPassword,
        };
    }
    exports.handleDecryptionOfPageFromHash = handleDecryptionOfPageFromHash;

    /**
     * Clear localstorage from staticrypt related values
     */
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

        if (!isSuccessful) {
            isSuccessful = await decryptOnLoadFromRememberMe();
        }

        return { isSuccessful };
    }
    exports.handleDecryptOnLoad = handleDecryptOnLoad;

    /**
     * Clear storage if we are logging out
     *
     * @returns {boolean} - whether we logged out
     */
    function logoutIfNeeded() {
        const logoutKey = "staticrypt_logout";

        // handle logout through query param
        const queryParams = new URLSearchParams(window.location.search);
        if (queryParams.has(logoutKey)) {
            clearLocalStorage();
            return true;
        }

        // handle logout through URL fragment
        const hash = window.location.hash.substring(1);
        if (hash.includes(logoutKey)) {
            clearLocalStorage();
            return true;
        }

        return false;
    }

    /**
     * To be called on load: check if we want to try to decrypt and replace the HTML with the decrypted content, and
     * try to do it if needed.
     *
     * @returns {Promise<boolean>} true if we derypted and replaced the whole page, false otherwise
     */
    async function decryptOnLoadFromRememberMe() {
        const { rememberDurationInDays } = staticryptConfig;
        const { rememberExpirationKey, rememberPassphraseKey } = templateConfig;

        // if we are login out, terminate
        if (logoutIfNeeded()) {
            return false;
        }

        // if there is expiration configured, check if we're not beyond the expiration
        if (rememberDurationInDays && rememberDurationInDays > 0) {
            const expiration = localStorage.getItem(rememberExpirationKey),
                isExpired = expiration && new Date().getTime() > parseInt(expiration);

            if (isExpired) {
                clearLocalStorage();
                return false;
            }
        }

        const hashedPassword = localStorage.getItem(rememberPassphraseKey);

        if (hashedPassword) {
            // try to decrypt
            const isDecryptionSuccessful = await decryptAndReplaceHtml(hashedPassword);

            // if the decryption is unsuccessful the password might be wrong - silently clear the saved data and let
            // the user fill the password form again
            if (!isDecryptionSuccessful) {
                clearLocalStorage();
                return false;
            }

            return true;
        }

        return false;
    }

    async function decryptOnLoadFromUrl() {
        const passwordKey = "staticrypt_pwd";
        const rememberMeKey = "remember_me";

        // try to get the password from the query param (for backward compatibility - we now want to avoid this method,
        // since it sends the hashed password to the server which isn't needed)
        const queryParams = new URLSearchParams(window.location.search);
        const hashedPasswordQuery = queryParams.get(passwordKey);
        const rememberMeQuery = queryParams.get(rememberMeKey);

        const urlFragment = window.location.hash.substring(1);
        // get the password from the url fragment
        const hashedPasswordRegexMatch = urlFragment.match(new RegExp(passwordKey + "=([^&]*)"));
        const hashedPasswordFragment = hashedPasswordRegexMatch ? hashedPasswordRegexMatch[1] : null;
        const rememberMeFragment = urlFragment.includes(rememberMeKey);

        const hashedPassword = hashedPasswordFragment || hashedPasswordQuery;
        const rememberMe = rememberMeFragment || rememberMeQuery;

        if (hashedPassword) {
            return handleDecryptionOfPageFromHash(hashedPassword, rememberMe);
        }

        return false;
    }

    return exports;
}
exports.init = init;

  return exports;
})());
        ;
            const templateError = "template_error",
                templateToggleAltShow = "template_toggle_show",
                templateToggleAltHide = "template_toggle_hide",
                isRememberEnabled = true,
                staticryptConfig = {"staticryptEncryptedMsgUniqueVariableName":"be8cf5f41eab9b8794ce23f6bb399fc84e37a6ac9111147af89313862438375f3b171dd0f3b5de6e9f341a10073595281d03a6e220a3d7429cd4d6e3194a5e2663f98910aa226ebb737373987df1ec56dc78e9bbf2a6a68e69f4427a2b9489c56deb1e5be30f356c5c0bf111ff11eea8275a58099d16dc23632dc077bf178bef168ce101fa75977d5960693636a2a735f9cc8e51f5ec683abc5b8a4a0c5e3c56eea6c3a9c2e4731f069f31b1afd637521e75fb88598a74247fbba1be28f4f1304b83232a94ed531a8f9fb963f878c6d71028b8f1e929c6a60efffe7341dd169b160501d50d87f64b686403d90ad267cfa8280f413abd77b5fca9fa05d68b2ae59011dff83a7929baa312777375abd876d3eac4a38900f8bfcdcfb6b5c17b65c139547fa647bd7c57e3d2e153b39819836c13f5b5faf87fd8bf4b4342b40640bba960697941770ce8639720165ba25e47604e5bc3c5eaafed2a31fe3b5285ad6f8bfa9d37fc05e596bca0623c46636de6838ebf1523d15e538688adbebb1bd206825c2e0d31d9911287f70436258d2a9bdcfed897f84444057fad2870ffad2ea12455c3612e8c4e622181807288334b5b2ecbf93c22617f884750088192bfb09291a89c93ffa4d3a92322662780593f15244bd8a32cb5ac1a3d21044e7a469e2c3e0b3949a15d94d7c278c1f2ce3598add9fd7eb0cb71857411f3a64d0ddffd6ca8ea873293a06ab919424def234ed59ea5ad8068235cace2f132e73a6ab7864ac1e4ae7d00241dfbaad64a052f9f62a5f5578d27f3952f2ef8904bf879e5120eddb081ab1acb53d6a4e422b38f6062a669bca73cbcc177501a911bc539e8f30825cb67fa3202b79602f747b6a0cd6bc833e8d9171cd4e47ea1d2e1ca003db6165ce93ead232b7ba25ff2196c217b37cca538e893fa12659d469c5368f06755a705afa6c1485f19d627efe0a6ec19622662e49d029cdecc1da0cde562512057c96b461d5632ae1fc4d4e6aada8bd592de370662f8796023fce5f96a4d171464948ff7843823a6b76883d35ef79540b3044b5723a9a5e5d214cca82e0a89f2a132ddf4e291c17ce4d6973f487ff8f2519a607a7069d89785fc70b6991e99c9c7639f72289d6fad3e021fdfeb61cc14d0a2b0d5a27a569b7c8db256ac423ddcd2869a47ab8470d68b3e67d995ee092bfc42c8656516bbe5d06d2ddcec43b47923c30e73e3309c7738c5cd5f536846470b9d06d68053f353e9ddf67ecc34d79abafd83b69dd1147452d20ac15ff2926ba53f09ae9809c59d3726c2fd42c70ff25afeeb804b2913b1f8cad723128e906e800f20a90f0002a69df605e8dd52928bb5f7a5a7e8567abfc22332d0b4af7494e4de7074db4a97cb485aeda0ab4ccae20624b8d2e0df06ca492073127d2703f3bfaf74316ed6439b6e1e03daed8d71a03185feb369a3d095f72b0c7369f3693318228d934b04c5dd50074099b1871f61a759d947b11335e2ebe4c6d120a0b660c37d13b69f3bb5e057d1a0e1f814293976743a7fd2d8c342bcb2cc72f85d3644ee302b09ca5d2feb68fbe0f2592034ff1ec46e6a7f99b8515fe32c17f4c905db6c3ae4ea30ecb58c554fde09cb9ba452f2b3e375cbbc5f8b40060fb4e328162dd151d8eb3ba2412b71a12999a84288c45e4bb0bb49542dd996b0ee29b0465d6101a97cf7c1a21ef217824c091052a17869bbb29da25259f38f0b053b094d9c4df4c72bc6020cbcf76efbd72c7e72c2fce08581392ae5699996fc55566454209c9c2b93b9951bfce9dd077a375c741c6a77965fc18e5f71aa97eac847ec1ac4b98e9b64858c9bf3f4c923daca0b2328bcb8dbb228f0afbffd2ad4fbf21a046a00c15e58cc6b333a7ed80a269cb0403123225fead98c51ee4db2d056df6e42a3ec25fbd5901f1c2fe02e39d1be5031c74656ac5c34a0a8d971c7dff209b82bb953df709039c09bb171c9252b9cbf8781613e761c79e9f167562fcfdd427735f54d8638375d7dbfd48db301970f3630e806b74036792cb576d33a6417cbbfcfc8918c5b7a444c94c6a44ff278abd2706233ee7a5ff584b3f2784a4721089d7ae98831a3d311fa4c9a51c84d26a4191ec0a1177609a0bf35d2424bed41352a77759263f6a04f804b8bcb2a8a5d95e5fe5d8ff644d9115ed080facbb4721099a51c6f00bc7b0172126e2b6ceec5be62f938e8350165654dff3488496cb970fcd4a78e7df361fa0080a41d3fb24d7d0f2ffe1137134dccd68d06ceb21f3db7bd3a9986987c68a7446346a8345f29cdd2260ec53436028f8f870f65fbe1694d843ff2bd052cf47b9c1d33ce7837bd9cdbef7fb59803d513ad876a554e136e5d46a72b789a65c08b2f41d3aa57bf3c34fc10ca0d7ef28581a3dffb15e08d628e9523ac11d709228f641a2262b76bb42fa8314b4faeb22ac882694fd629db68bac68052c5303f8eb71cbf8c49718e9a86752cae3296a591d2478c84681a44842969465340a7bf0af87a3cc61aa252533ed21db1ca8536a9369ef03b4251979203a225dbf1dca8a438e66fcd82528fdbc743176a9befab4d894a50a9e7e80ae9f2ff666b76f998eb6d5c8559387ca2952f19c50bc1c2f4d67f8ef634ace23f2c42d388ca796655626bdcb8abeff0610fa72c09a324c8edfcf6b06dab42cb21e37c0706b408ef3c036c10c84112d51eb6b610697bfcaacbb96660fff823c8a12e29c8817a26093b6661cef5b23270921b9b8ef90554901a467de8d8f676d6a73aa21722de7b547bb5140b0b084a80af50340da906348fdd5907c54a5283c6c27f699ea878663f2629434b827bed7c33d8c66802cca9bd0a779e4229a64c289d331196453b6f49b74fb7e3516665b5f305b3819d2bb8854a5c04723df01cd24952a475836a864dd6c47c36530bf9f189af736e8f4ea4aeb784cbee7f956c8dd2a908d6958b1ba38c7f49a50fb4d3e2a6bcb79ebf6a3873771c9f5d2c794cbf921ccd71f09299be793785e2954214ef6ad44bb38717a0b79d8032a864df7ce1fc3e3ddf3dde426ac8ed4d750d8ec8c8165bb19ca7ade406eb4a4cf5859b2c5300bd8adb7a6a41652c5f8c4bca14bbcf948d874e411d3602b956c229c46dbbf264e4848516330e09efb9911d2f5e522e23ea2897c270362c9f45e797c82d44fbb61dcc1e0e3e012003893ebaca7fe8a1faf26e2c88c5a08bdb12b2195ad11669f2630d0cd988e3e30d1f84e6ff913b88df9ac9ba7a2eb2c6827dff79700f9d59d38b94f74d2beb6a88a64894ed5503b7ea555c6725fa998c125671948348fb886c69a493656e5399cec78429ebcef9905674a27a1034408b24de67d7346a42e0bc1628806170ec50b333a0b148b17f488a35704a61b5219e8f217442a99a4bfea4f2d00593f83eea2c47e0101bc3197e853c50291d6e8b92c016cedf2ffeccf61dbb43339382203fef73e984e717e970a3094d199307958d11bfd62a14db4c9d3c8f36fc9d28d044ed7be2f021765a3df8a4a00c66dfd1e2501d0f30462aad1121149055616efbaee63cbf5b52fc2cf3677e84f45e5cf3788cd24f6a95580b346f5f4341eebe464ff16d18019afc9341720838d8e5f048a05ef337faf1cbee36dd2ad8a5f2e52f1be7687e0c7cfdf45ca64324a9c28a6a8f3086f854fd1a44d68ec3c9fd984c589ad368186d831b5a3ea54195f5ee328fd7e254d3ae694d12a1193067b6d0433e3ecee9a918034a77cb674ebc78108bce7b5a13406cdcd0cab9df08a0a24eb3bb82275fd7dc63bd59ed44c0b2e207aabcd2df3761017f68fb48a992b1616782c68629e2bd5208d78b09327683ebc749db506ff8f46aeadbebc6355d5ba2ffebc3894d1f1cb8778bc791c2326b65f0c3ed219041f772e876c73953f279eedf2f7389475192fff5df393c6fa3814f01f904afe7e013edb342421be4908d2605f275f455a4201b1309522d5ee242f90900ee03483e35ba4a826a3806545c6cbbb70ecf3510036bfa10b3aa99e896ffeecf867d9e75dea2a184b0a5274121ba4032319e990ebe1553a8850369e88594bc25518d19525dc1a536943da78e9682266a32588a410a280f6c0c19e3b672c34c0a4b72341f15deeb34be6b3c34ecdf30e5b071f3054cf99cd0d32fb6f64eb24db03ff3fa2235eee5ae557189057b9aaeaff704f82984fe61be52da5f4b8dc8c88f50ec766221900c89afba26b8bed4e9480f1976210fd362dfc1c8e98a5c347d67341bc1c8935d0dd452d62335e7bb09887bbb9f0936b67d8837fe672a4c13364e8b52952b02aabb2ef5017ccae33e86f013635ba90061867d3de94e6e578aba29302518a0c6f87bf9a4f55ecfc1fe75bd6bd67bf138ac9a0ac5e4f83f34cb1895a366a4ff6561daa703e8202f050490dcff6e5299cd79aa3f9efbdf080f286b84be62affa5644391c435d714b3f4f926440e1f40e79ce40d530ee29c13d29f8304ee4f4b4166141db2f5619c5fef27af790467a6854a7c9769805df7f75df66538c7261c973be18608d2d2be86144c3193b4db79637e71498c99a31eb6efc60d0cf5adf39e22033b80da2c08bda965c0c002781d55ec353865283a0473a84151aa34aa70568dad74c71539a552c3e2bbaf2daaafaba807e8627522b1d179b8832d9831126ec242cbed129229ea70b01c3a049a98f1e8b49016395086291960685d3c15c17ce936737623f720602aaab0248ab345ef744e00ea003024e392b12929e9c8ef50d64923785151b159ee406b943c8f2a0fe3907abf08d6367f311667da27631a48b32f9c23a5395ad0e3351c15cdbcd22fc6b90095ae28f2c6cf0ace245efd4dcc7401c7b0ee4bcedd924b5d913c8c3285cd413a6a171d02224bb57affb1e1728bf8988802dc45c86c298ccc9326f6e540b2edd1d57f6084d454544b06885dc365eb598da915bfd36706e5c80b810b60cab4235d4aa11cd1ed969a48cf69a482fe6386035fb308f1674dc933c53257bff7da96ad21c8d029ab996e644a9f29dd51e13e684eb06f97eec2c4fadf81a730a4b3f7f83244b4c95070f51d076e589b4e562ada78357c59e248439e8942087daa7b2d5ca1eb006ec704f237c100cf9d95b18716d39f090ac4a4155c70f37cd12fdb266920a40fb54a12df47e389d3317bc3ac830e20e024ad0603aae994cd9032e3db995d3ce723fe933ab46b70e897040087079e8eb786c47fe69a5bc24e9045daa9cdd6d9add1af881521de6d245ea8fd08baf236967352360885a22defcd41e771df69beba9624610d3e81a8ab8af2a3e5f1fc3e06e982faa14739edfee9db1cb9988ba2c7d34ac6ecbdadf6622af6f3827c4ae59a3d72407ff9c8c2e4be625ca2ce5ad23694e6fea0cce3bcc3dd247c4a9dbf6c850da61742b5f98497424b1f8c5c048cf1a143d4c3e3f9e5dc00008aa39e7216536fbcf9cb6296a13bf1779c89141a12c5aef1575e7146dd2c59606e510862a3a1bf61e17286b1e6eae69581ad0ff2d37d2a91aa9b18f37b7e235d44f6ddd3fb0f3ca2595aec80dd7f198c4ab3d12a7cd65d994cb60df888dc20348471a537bd40793bce0000af04aa01c626db5fe68e7908b106add8944110075cfb2eae88e9161e85682b1e36ce86be80733639b5f491859f02c6eb0f375f4bdf210c4409621ebface23fa3d414f652de906ce636d911dad95a0d1daa6d231385ae82b0e75b7ae723f04392094cf37147e4d54a105fcfe6d90ef84254ec83f41b2d3a2022537839a13530edb1da6089575e3cba0601cfb194d1797d1db0395947c1e56027ab2068360a2ae81e45e0bc03041b0f99aab87ed7a3d3ec640b2f1018246b694b82653a25ffb136008fb228b4b5b65f6ece86b78273525cab8472b013803f84371fc732d3fb3c864ba93e5c66b9eaea90cd793713fa4f3fca430a12271ae930c2e2025d6285341de7b44ece19bdb34f96dd694d7ff54edeb0ea36b86f387946c38fe322e8ff9bbaf8bc32eaf862e15af1a5b326ab18e7f5e57e3b6b55ff7054bb5b1490fdccc28be7ce9aa6ef31d28a8dac24c05378f6b5084864dedc3c22c18c6cfb0409fc9af76a3eea9ee08663ecfffe4053ee6533880004f04cfddfdff179f9d9fd473791275d9ef5552b60748643e328f31203d885f79c6b1103f4f5a06c35a55d5767b34d50ec75ff802bb25f4e19d78c3aa71bdf36891d16d29ae83c93c73db075bb4699c39f75531bb8da69410a73ee5f531a9ee1a7d9151f13560e90a1657c230690e485bda24eb85e5b2bf1d0489a49a33b1b30fa30ad65902ed8f5d5062f6397b8820bf0cc26d17ce1a3ec908ed2a82c835c7623bfc51c9285601ed4b7df12d446b4bb6ce359ed03988068325c7d6c2e83bef0b8d33f2b81e27277010ed992dca9596d4044847919e4af75922a89679e8cc0a1ce6fcf0bdea900465ec7977e4dfea8fee2d262d70d6d8a6ab4fe363373bea73882ab9c3253928d93b694ed191110331ea461652d0a23592465f82d805c83c47ba3f133b5f3782f6cc58a38a9bddc00fe18f21203960b666339e2bd93724b303ee4bac89fd644f6506432d0876698cce838792db3310a6c0d83e6bf433421109b320de74efc195d22500b42fc00e796c64d85da40edad83811809ab5d306fb1fd3252036024f31e08e37e5fd983b81c2c0b4f3925ad04bc70c44ae1bd1d061a412f104fda9ad7f4b3868ca51280a04918b0a5a8c71efd193ae65eb2aae41f74cda8d6cfa0b5d667b9a1384088951d708f93b6ff2da4c9c75d656b27b16b2dcbc222d5eb6e628897d202269b911bd2c923c37719480467cd34b954c5d920fa7940e6370f7cbb293ab507ac0bd740f9606b3cbe31dcfed17b8d33fc24cbaa96363a8a0b96eaa795c5730a2ded1c170367f897e622fbf9f795b7acfd3484d2085210b0b8eb23a8aab602eb9bee78d7d97b0df1270d330e2f89b809f77f2f40e78c0075f7248135d0158c68778812a2eb0a4915cd8dbf8a3d7fb41ad033b908ffce1ff1eb7909dcf1351cc01c2c2d8cf0c00eb448970cd137720190ef2eef6c7ce50470db7bbc14a912f3d54b682355d12c43cef70c267e9335e018137c28594082f614100047aa49256af2593d459a829b8cb22ceb4fea606690c55771bb0e02bce61c7d3b201cfe47f48bf752a1d136f5826b547332b4701f6cbb854507db2fcfa274b815d92c16b223fd1b333c97c1c44cfa8e57e7b2b2692a267f2b2709d9928a55c142fab780b24c7318e73cf4315391d06cd6c629f0009bff99be94cea1baed9adf35e717a7238e0237760d9db7578b368786a1abff4e79ac1c36fc5da4d1830926dff65e3a64e1527bf3ffd40814d1c4d0f40e080865442a22a497481a8fd532de81a9507f0169752eae82550c4ff40daffe016b8dfd6eb806d40416d3e47c0cf89c2bbaee4231446cfd686ff1888364f9a3502fa867d3e46c06c51829de6d7741431b04b903caa85ca3f92aa33e7ac01ad6a9e569287ca309d374bde579bacd172a2d356c221d863fe87ad62affeadc36c7d5d227fc432f7f3b30e235b6d747d619cb1036109f8666fe47e9555bc84f3ad5cb63b0459dfe08a1696e00d032ce7047ce5cdde78e08bb66db3aa95737d2dee0cc47f736cb54837194f91fcad694282de0660f8364a86223cd94f234776700db0255ea404b4fbe9620661a6c6ac0a61eb01d75749c354ea3509c5f7176ac004ccd3e82cb35728b64fcafe8f102c9d0dccd0f8890be3e1132f160deb044f7e99b0a07739e85ffd09684c395387af6fb7e19a83021d63caa2f94b853be69f6e462329efef9ec93c29084f340599406eabaeabe59936fce8f3265af4606a78b7940dc0282ef653b910566f7ef21503d5a30cf568f066f0137393f96388a2bc13f194af1fe48326b55e60d025e7d6579cc4e02f575728437c7075c119670112a10acae4e9337a922e4d6ecf99377b386b0b978d1aee1dc6e0bc1aeaf1d294dd45d5081be3f7f8ecc402ca523b240dbcd49f8341158b40cb631a9388de579494ca07f2c0e29f23b47d9fd81d9dbb03677fd51970246875c6b533296fee93cec9c9cb1fe9392fce7f37019a79ad2dd6f79db9fd999368056318bd6b8b993cef1475aa1e87cde2c0d8420357cb8ec8bbced42108abf3f166e941cbb1f842f7eb9dc7a4f474324cdbdfcfb1418e7ef21b7ea160773ba5fb90672ca31054a1e91320b33145552c76af0f89c7fb8176c3a65adf9cc45de49a9159c026d1a2f9d1be57ea8b58bb60757763b518a248e01b5aafbeb9f47c29d512baaecca82f09b364151f1dc2a3f295ae3efa787e1d8ec94c4ffcc00d4547af16c02638999ef3b2e9416a9341b364d8023cfdd8ccef37ac86efda7391868979fe9128d5af6ad8269d28f0434561528a71084a0ea2471208f6293277baa48ee9d4c580674f73bf023c25bc8a2d547fea4e9084b8fbc494382e62053a2a2c841eb843b1623df73f7f7b0aca0ecdf9545091e567d80a5f873608d0d5c809655a747a832c0f51e874b4bcb02b14a8a20841ac0f658ba2c61a3573e5e2b1bca6ed326b97b4de4f57845807aa90e3a154b0e1c16e75bfc2a88e9697bafc25ea4aae20faa4fad16b901ccc465b413c393c943837291b8e68a823c8887bd3e071dcbb44f080e337de0096d0322caeb71603e5671cf24890c343a88b59dd722694bc56bc97b1756ba88fbe17ccd03ba0798a945f3e47f1463e2abc5fdc89987fc42a6d86607e35ceb29a1176c9a8db32b36f3a41780f49a4e3a03b10a270a6f5f371a3687c97aefd71359d0bfe24cc3ed407d6b50402bf0465bfecc21f46358495ff4fbfd9afe8a6d2dd6e61c0592780e78921a100227596e9d9ba21d92b06c1b83ae744b410640e449891e3ca2231ee6be04b377142566ca069b552c1a1f6b386b6bbd73faf75a69d231237521599db72215f644831d36db0c2fdfd2ba936b56503171672cb3396536c3bca5ed56323aec573c24ec2b30a3d4bab7304b3da03c6c9c0b1592e16209a2327040246bae770c3e56fa39b45b7512ca5d15e5fe34c8512886f052b34d569edd041b4a6193726c51812a94886812f5b1295ece948c4016a836442119b47d07f2ada7901fcebf7a4c6e68cf911f84d3791d6497df05b45646613cc8fe35f2dbf20973c451c2f85d5d807e4f0d5bdafcff15dcaef8e999c8a4fb0ab122976aaa705b138cdbdb829e7dbe491a28cf2dec6e506057a4f8767dd87d340652a7df258f7d76057119641cf97b09db9faf1467d64e7279884f0667c86a5b1551bf78b38b42893830fdf3580d43c25dfaae113ada912247351341077d9bc7e9bf1052e89f3a00684e499c03e3e78f8dbaa77e2f86746f4ae4cf81520ba4b7a74664eafbf5e7e86694e1bbc339421a8a061a83ae004e5b8ab13c904ab29c9b249043a09bfdea7647cf81e721f17455dacea4f5e4d6d800fc5c94332edfdf109a6b045404f8ede43de42f5092d6ef9de24f531843ae06548e01224f23289e34a07b038e362710da8fa9d256b5ed0b502f2bbca16083df965bd6eed3510561ece9a9129a735a992daf4e4d8656b461bca7a69ed091fbfae282c59fe1efa9f3af04e1966016eccc87964b1f22dc7d3dbeade88c81e9ce4f86e17bd82477e27e34d7ec5dcff83e01641e5a51f742151b051c359e6a566b1bf593130838b76173a4301a0028ba90946b53d4491ea849f48377d2713a4a4d49981c10f6800de1eab93b0a57804784a0b81d6cbc48d0456bca8a02ced8e430a6d145501f8138f8f95e5d43c47c8b8f7de4233c8fa11b0bea9bd4db9a5a8f29622e4816e0f78082809aba2a0a5be3e636874daa7db125b0873c15bfee8ba591a4756f060c166daf0a8775558faf887913e6592d280fecca08917ca16cb044fcc87a0023f50ad87bc1bf36b8d206132772d6ad499f8d225f9b61fd4dbfda694723f164b767977f081058fcb3da7585e44f4259e53625ba7e5fe7fe2a14f33c815401f097e6efd815df671a54f7502c57d24335d4a6a1955a5c1454594e9f3792075059145d2796e4f4d5caeb1a41dbf465de9785b0186d5e8cbec6b75aefdebee168e2479d49c09e66d2160dfeb3f08f62cfe3440d4cdb70e5ee8150c956fd12d3851fe54ec5aac8f4cca56c134e981111e802af23ff8832934f57efacc8cc2455dbea4abddfbdc36807b200a8861e5e8110fcbe8e527d770f5bff44246f785ec7c4379cbc6f4cd2317d10d5bbf913b5c612e165a16d5fddae54d7dd4c958aad51c91f3a0ce77c68e9102b8b711fcb8055cffcd2806808fb26a6f91c68a049314db9349f2803adaa4a4c71db7f42a2254f40e2b079281d20521459e3f9241c5ca413e05b7eafa3593015a31790303db4d88c615c3f431bd4d9e643b6d3056274f30b62f549036724ef41bd81ebb14ab273cb06a5c57456ee33dedde146483cff5ae559034db2c1b565359f4a05edac64c207b0526d885e8246888e63cdd1bd42abf60a180771cb20ff5d86a76b507888351daa4978847ed56930efea77403ed804f5af47c10c58db1c88cc34464d28709ffcce47f553fd0428d8899d7d731f93f9d59693feac09626aa159dd77a9eb895e48e0b98af27b48d4ccc9ec574d5b7053d18d38c6cc855b266ada78774844226e959aaab5d345c92f8ecce1c21544d2803665a2ff29dd01c65b9f6b4d9953263f1922da5ca6ffc163f86533f4cde1b6177688b6dbaa56c99db8ab52b1cb034c674c0bf3ac27cb147037634cf582d9e0650d75a08259309269f30915705dd8a966d408bd834a943269249bc9dd4fff949d844a6ab142a16231b4879599cda617d544d0104ac4af66d5d2081b76a727cd3011d36ba2c2438685a3926157cb10adfa4fa27d0f4b450db0d2b8bfd88f7b38f9176c15f9b508657169555ac3ba109fe3435b2a319af87452c6dea3254a6a67f64e56c331f9bb7bc45b537574ed4b8ddbd10a10ced3758584cea01e260f0baacffc4e864f2ae6e2fca63b12199f7d5bc526aef6ad48e933f4915530689a6e8fd3c130fca758f2d537f47a8dda06e6eae240d738212e38728deab08acc037a8cacc5424bae3d6b5c04417dc86f8a4efa37da6dcd7604ae7885c98edb02985d0e6811b3ab5eb29152b24f5793265a4e4639bc5456ef581a9e1cba3e3536735afda9633927c50d455034b237be8e214dbfaeb520bf976b91763514a6ea09399db14b577620ffd9913d54d80565455f50f48d931cf10046d4413296f67e6ece7cac3ed5a7713c06818310943963c67fd3f591d8638ce4da6af224308b647b6e1b780ed6f9004904d89945093813d2fa94e3a13f41a21b8ca729b5dfca9149317403a5b18027c19aefa7de8e7ee54573660dfb237b1ba277abd4cdd1f78d0137cfa722c6af23e37946072e2073c73355601dc1db5d6dfb87b8ad59068c6b68770d49fcb469001a409355bbc6311b7a291f1ff786a1f41984d2eea1044fd3f65ea9f205f316e1010fcd0cb52378944fc3326f19cd13d7c92ccaa1c9bb90824ca560bdddeb89c6ad3e9dcc55d53c8feda4b5f034aeb9613331311b2ad06e2e0083039ab955fe759bd7bfe78297b7e54622b4199539322055731fc42965f6151801c47240d080ac0b07d842025fb47888e24a1f52e327997f86ce1f86b7b10365e60b796680f2f068702e27cc6edbcd4f35f12e530c19b3d15b1ea9a5c71502b349eddf634097f8760f6bc7a7e47d705ba50de24959724c306436bbbc7b59aa9053d3a54e3faa717b99530fe38fd77b9d30a72ee585d4dda254f47bb8f13f208af4cdeffab278f294399260d335248402641d7e8aa4be5f54329a45bcaeef1791f3183d613fecbd30b9f4545de5a893d4746989cf8178567f26d343fcc9b03eb70166f92c37bc361d7f398169c2a06505065dcc228999ee7c7ab3c1a3458a340a0d2a8ae2ad887373852dd111a3b4ef98fcc11fba163c88ef826e6a66d68cf587f52b9036252a521dab1419fb7b449844124c853f0a34e62f835e41154207e1a2b2e510e0b26ce5b6d82eadbb7551f2ad19e9216155951da5569b64857c9db830c7ae44342c492dd32f9fbf50be3698eafdf4c6d6985237e9cd6667069644807b304277d50f499564d284b790a2369267a31c9d370d39fb9605d5fc46431b340e6c290db9bcde091208d9cf1a0bffb5cede0b7afdc569bf3da5e9dc3af82d152744cd4edd8aa18c2c3c9dca05c549dc905147a9ef31c2079cedced7d315e0f6e6de285ad7db1569df19875321fc074c18f2d8f9be4b37c82cec920d21f25c31806cd24bb21b7d843ca420253926f64757e07673173add7a31b514a2157aa1398ea692a5d0f0f212d5435e01938b5e7b2321dab05514d219884bcbd33d0bb8fbcf8d61d9942113de35313889d333caf2d1136a7eed2b3d7aed0088fdf19497800295878c9f6686cdb8143b6b9b34ecfa4a699c7bfd5c7a7d6e16a956f9ba5c3dfd34ff9378fe48a7afd712e2cd605ea38af2c6cc9b51dc0f25bff9b51116e7b939c42a82b93c20967e512cc7634ac88bf78b16b59e98a21dfc1166ba07a1de4fe0dde5ebe60ea8217d13c23cd195a6cbf2f13373616c1734bfb7ca20a6ac83a89a4ff1af1af07fc460c057bf70cf2bcf8d038d8b911ffcb999b62f83007821ad2e7283000a97ccfa2934dd7e20a83178c52cef6a22db431bfd50821d07577a6ccda80d926cb703c1a46be7bacc5fbb7fece54c5f9ac3da22a1bbbd0c2452089fd28ee5cebeac303183fcd833b9406a62c5a54c2644bda635f84d7b6f7380e41fa6d98137ed3bb6a1b70f1c06c2104e2f41150ab9b2fe181e969d3bb0e16e42b0a63d301dd696f8dbaf06b8fb626ad8b64be7de406f0c74de9bdd4e9095c8470565b35d41966a409d9c176bd25c315609e5441e044d5e920acd523cf7681dc7daf6086148bfb77efb35777651735b8cbf62987361ef4115339494d8684dce9f1732d8fc8170e978bfac603235066b4a5508b27009153dc6fb06090fcbfe21442653e71fc21f72486cba0c45411645a723539848c40c87aab8f9bf001786e7e2a3a1ecbdba4b2c7c1b57800a22b333ee459492e23d66c2cfb20d3ee12e0329f94ab758b29a4f84389ed602a170d69d14eeb5161f0f933e67770de08e351bf456f0784475fee9ebde5659682892ab759b548e4f7b375f35bb04c62508614833f458e9a5adc1cc070ab2525eb976d92128004aa8821d7342bda77367c131e3406990186a7cb908ca936f4406090ba799dc1bf286710be7d5b4e138b83e994ddda792e9ab94e7b5bcf9f57c10f70a0760e3296b57ca9ee7b479a9f54830fe4228b4cfcec2b3d4debc5e634a5d020aaa2f7a01814fc3d1e71e30effcd3ac8c91c2cf1bae4bbf2a05181e6e290627239dabdf8765e3d4bbefc234ac8fa80c55328ace2ddffd2fabb3b26737127d9f08ec5e989d66d015ccccc2f1ac95ad553662486201bc7e414a1750f73fd74f05dfc059870ecc9b759b2a22d58bb8775b69310a5a7bf26703c54c1f6948e96f133f849cdbe0844bdbd82bfe43267641899bf547a3df2ab3a3ba2f787923e41e54831c431649ad10849eb9669fe70ebc5ff1a933709b76085b20736c5011345c07697ddf90f52f0357149036ec72c7269d5ef1860f45f4b48339324e3c24398b2f4344419b45a46e48fd3402eb8745fe665329ec8f54565ea0d109fe1354c71bfbd4bdd0729fd26c73c196cb001448838d43266f48f46bc6a109d13103367a355c1eb383ebbea4d88a3f8dc995933657356869e193d38e7b6c2bdd577f41a0a0a514c33458217c5cf5900fd753f79315d09d6b43f3c7fb435e21e897a3c14f55aebc97218b559b8a631bd8b904cbfb30eb51055bdc2545f5b77df1b9098cae896be8b86a9f840b42aa80b4f5ec918d04ed010f62976abcaa6392d59e97d2722e4cb7637295be657ea75dc88b97582acbf79810a9237c4455a3975b4ffc831ce4fa4cd8b13a9c64c7ee9d5210a2bdf25fd5ea09d7fe92ce62eaa012233a6216882feb4d5fb65c9462af7bedb3cd82908b06892ade5ae8bd42a24e7d50bd87de0eff57eb05d7860c811e82b5a7db8f348e3a827fec5650fe90b000f05a36001c05959b25de437f65d5e8e0317920045aacd5713ae44f2b0d3895410b67a321dc3aba24b787b55649f4d091fe520f9485cdb90591bbecfa88c19122acc519ad06893a75e32c1c9d517a945ace5c861027a83f3b38ca3e3727671defc3f0896fb7cd1c022c3018194936991c5ef8af62213f30458122955e827d690946f6284477dda4367e14fe68827df6bd7b2c9e258e7603619407a7a223fe71054f341b9d1441b67f561592ce1eda7baf50f76fe07dad7459d8438a6603962290332f0374a0f4988c05929be6c23ad850a09a0949c946827cd7ba64461498b666d2fbd2e52078252c462af27e60a2157f3f1656d0457458566b17d121d8ff46ebf56695e39e07f71ab90da429affa8fe7fc3a114243e319f543891482463e81b396ecd25b45b6af6610c4e6cdace6624df02ff5346640b2e7da4278028a6294c50a5a1ae08031c84c92829222ca6de50b226460b1c1b861f2186325f58527c63f35c70f5fa687f02903b954ddc0495f8893ee00fc4208fae32ff772d33f79606229f3695679fde37c31f178b6b7d5d93e195b7519beb99919c5c417f80f03c66ceec8a3672336c5254dc7b43c66690c5c781bb4ed012e960e3ecaad2a3150e658a55b0038a93d5dc1e9926970dc717ff1cbdfdd36cdc22afdae597f6418c1dae6441313d40f500ef0712a27e4f36d6300d943c56f60aff2559cc4ec8b7d024e93fd71433b34d8ddc31b666fe165a44a94a8a55f7129b5e23148e29cf2671ce9cca4b1d7d85c62381e6ccb31b433ee0fd2b80e4738bed4fb0e9ffd60efab279df247daa7a081ff88d65217c3bb51fa0d1ac297ef2ac9fd983b79363d59fa05a17bec9ef874db05abf1362fb4c6011120dfdbcb22ea0e7e4629236f51f524abdb536e743851a9f6dc2851b1cfad60653db544925967598426343ed5791c1fd9dea4e4bfb9d77277b2e27dec0ebaec8adad6ceb2558e3402df24b54d1272cf9f3e0d82aa5ac85c40483522f25119db2fbdc2269659dd34eab1f82450c9e07aa74e1797552b79c6a7d49232631607599600ccbbf8990eb8f83e6c0b3957d8a2fc343e44207ac434c560187836cf867c885ca3ec47e22e1a98978ce84de5da3e2a3a1bad909e7f548a3eaea614645e00acaf6290d41ec1aff603639809ab900f43b1bbe53312d3aadef110b03c922bcab37577147fa532e8b9b48ea0809cf97f1cb451a81d2295a88091e384b8a332616343cd9f926ca936fe342b155d33b9bafdec937f8b1fe3cc04bb326e8f88bc43d99d87e61da71cb890c7db825038930b9e1b6dd391719d38d2fdd6e0f4814ab6d607745373c8d2a599290fbd3445a8a3faf343445422a7dd8212a55efdd83995e242697177d015438aa1ab8da1dcd79b23349fe243d9423e05b536618360b391e2e18672c0eb9b801214185fdc88c3f6711763464c304d3bcad78ddf5d5ccb8414fe2239c9c187ed37db37c631e6fc25b5f02146943223086568edf3f0a3f23e3c247eb05d2849a9045ad680c5bcca56067a39ca5018da30fbfe56b110e99962ad18edc36690f991b1c20f7be8f728733d2867f9d30540ef36e45cee045ac61a70029a02fb8ffcfb1a2066d328d1b3cdbe1c50e528c10fd4a4f1078104e1800037df6f5b08fc33d0469f27b3b0c3d85a70fa447f643362646046587a52eaddd9ea5a781735eee8b58388640a784977781692996341c6c33d1735f1c0b659e86658742096887dd8b2585319fae7c23bce77a8eb0b72a42bf26a4264d64699f71790ad1b2d0076485320da7cb4b15d8df7cb7427dba199fbc23f8680f845e211a3cf360872032f008834e192951b9dd3df801a7f80831817005df07c4838ef2378b7316294b8945412d3e8181d6853d4ab531c1f766f7498e4383f0303216375381d2d7440eede3020f33c3346e2c13250b999c3c15399902f4a5126bd1c7e73416b29ba68465b2eb864f0e01210857152cccfa5294b30b80093862a4d33fe1cbab62fb688abd1882bd4b704005e64396ca7ceccd7048348cf839b8574936e8390b750bffb2165aca5f0368a3835e9c667c6f2f89b0e393b456366286a8fb144731ca006fae2a183bdd20d86dbc061b3d0ace5a3e1721c087e60183c7623194c1fcb25ccb85e27d1e8f63adb5f9e2b444713dffb2eb1234eb504a9ea2afcc0321199c3a1d6161846e9e8c9d9c2447c6ad649c501f2259853809b0c287b19a340fdcf58aeaa81339b0bd918e601f923bf86a06da36525531aaa6ff526527a7ed3a7949f5149be4a51d46a38ea42854f7525a0d87cc4d5253912c74fe6668a54bf4ae894586d1a6e014374de7e043128598f2f365ba8f7f462ffe4d417c313662bd7511380b85a90db43d0c8cda98e2ebec0c913c4d3ab11ea10d71f17ee1e4839f3231bec011e2cd9c68e02e3c3148bde4f01163eaa54dcd603050249911a4f8359d0daa78cf062cbbc17f109796b019c3ab3ff17d5b0cb740abea2971664d780ac84837ba33702dc6ec5112f282d04524dc96e6c7af7bae3b73","isRememberEnabled":true,"rememberDurationInDays":0,"staticryptSaltUniqueVariableName":"61fd41132da05af6fcef1203109b452e"};

            // you can edit these values to customize some of the behavior of StatiCrypt
            const templateConfig = {
                rememberExpirationKey: "staticrypt_expiration",
                rememberPassphraseKey: "staticrypt_passphrase",
                replaceHtmlCallback: null,
                clearLocalStorageCallback: null,
            };

            // init the staticrypt engine
            const staticrypt = staticryptInitiator.init(staticryptConfig, templateConfig);

            // try to automatically decrypt on load if there is a saved password
            window.onload = async function () {
                const { isSuccessful } = await staticrypt.handleDecryptOnLoad();

                // if we didn't decrypt anything on load, show the password prompt. Otherwise the content has already been
                // replaced, no need to do anything
                if (!isSuccessful) {
                    // hide loading screen
                    document.getElementById("staticrypt_loading").classList.add("hidden");
                    document.getElementById("staticrypt_content").classList.remove("hidden");
                    document.getElementById("staticrypt-password").focus();

                    // show the remember me checkbox
                    if (isRememberEnabled) {
                        document.getElementById("staticrypt-remember-label").classList.remove("hidden");
                    }
                }
            };

            // toggle password visibility
            const toggleIcon = document.querySelector(".staticrypt-toggle-password-visibility");
            // these two icons are coming from FontAwesome
            const imgSrcEyeClosed =
                "data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCA2NDAgNTEyIj48IS0tIUZvbnQgQXdlc29tZSBGcmVlIDYuNS4yIGJ5IEBmb250YXdlc29tZSAtIGh0dHBzOi8vZm9udGF3ZXNvbWUuY29tIExpY2Vuc2UgLSBodHRwczovL2ZvbnRhd2Vzb21lLmNvbS9saWNlbnNlL2ZyZWUgQ29weXJpZ2h0IDIwMjQgRm9udGljb25zLCBJbmMuLS0+PHBhdGggZD0iTTM4LjggNS4xQzI4LjQtMy4xIDEzLjMtMS4yIDUuMSA5LjJTLTEuMiAzNC43IDkuMiA0Mi45bDU5MiA0NjRjMTAuNCA4LjIgMjUuNSA2LjMgMzMuNy00LjFzNi4zLTI1LjUtNC4xLTMzLjdMNTI1LjYgMzg2LjdjMzkuNi00MC42IDY2LjQtODYuMSA3OS45LTExOC40YzMuMy03LjkgMy4zLTE2LjcgMC0yNC42Yy0xNC45LTM1LjctNDYuMi04Ny43LTkzLTEzMS4xQzQ2NS41IDY4LjggNDAwLjggMzIgMzIwIDMyYy02OC4yIDAtMTI1IDI2LjMtMTY5LjMgNjAuOEwzOC44IDUuMXpNMjIzLjEgMTQ5LjVDMjQ4LjYgMTI2LjIgMjgyLjcgMTEyIDMyMCAxMTJjNzkuNSAwIDE0NCA2NC41IDE0NCAxNDRjMCAyNC45LTYuMyA0OC4zLTE3LjQgNjguN0w0MDggMjk0LjVjOC40LTE5LjMgMTAuNi00MS40IDQuOC02My4zYy0xMS4xLTQxLjUtNDcuOC02OS40LTg4LjYtNzEuMWMtNS44LS4yLTkuMiA2LjEtNy40IDExLjdjMi4xIDYuNCAzLjMgMTMuMiAzLjMgMjAuM2MwIDEwLjItMi40IDE5LjgtNi42IDI4LjNsLTkwLjMtNzAuOHpNMzczIDM4OS45Yy0xNi40IDYuNS0zNC4zIDEwLjEtNTMgMTAuMWMtNzkuNSAwLTE0NC02NC41LTE0NC0xNDRjMC02LjkgLjUtMTMuNiAxLjQtMjAuMkw4My4xIDE2MS41QzYwLjMgMTkxLjIgNDQgMjIwLjggMzQuNSAyNDMuN2MtMy4zIDcuOS0zLjMgMTYuNyAwIDI0LjZjMTQuOSAzNS43IDQ2LjIgODcuNyA5MyAxMzEuMUMxNzQuNSA0NDMuMiAyMzkuMiA0ODAgMzIwIDQ4MGM0Ny44IDAgODkuOS0xMi45IDEyNi4yLTMyLjVMMzczIDM4OS45eiIvPjwvc3ZnPg==";
            const imgSrcEyeOpened =
                "data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCA1NzYgNTEyIj48IS0tIUZvbnQgQXdlc29tZSBGcmVlIDYuNS4yIGJ5IEBmb250YXdlc29tZSAtIGh0dHBzOi8vZm9udGF3ZXNvbWUuY29tIExpY2Vuc2UgLSBodHRwczovL2ZvbnRhd2Vzb21lLmNvbS9saWNlbnNlL2ZyZWUgQ29weXJpZ2h0IDIwMjQgRm9udGljb25zLCBJbmMuLS0+PHBhdGggZD0iTTI4OCAzMmMtODAuOCAwLTE0NS41IDM2LjgtMTkyLjYgODAuNkM0OC42IDE1NiAxNy4zIDIwOCAyLjUgMjQzLjdjLTMuMyA3LjktMy4zIDE2LjcgMCAyNC42QzE3LjMgMzA0IDQ4LjYgMzU2IDk1LjQgMzk5LjRDMTQyLjUgNDQzLjIgMjA3LjIgNDgwIDI4OCA0ODBzMTQ1LjUtMzYuOCAxOTIuNi04MC42YzQ2LjgtNDMuNSA3OC4xLTk1LjQgOTMtMTMxLjFjMy4zLTcuOSAzLjMtMTYuNyAwLTI0LjZjLTE0LjktMzUuNy00Ni4yLTg3LjctOTMtMTMxLjFDNDMzLjUgNjguOCAzNjguOCAzMiAyODggMzJ6TTE0NCAyNTZhMTQ0IDE0NCAwIDEgMSAyODggMCAxNDQgMTQ0IDAgMSAxIC0yODggMHptMTQ0LTY0YzAgMzUuMy0yOC43IDY0LTY0IDY0Yy03LjEgMC0xMy45LTEuMi0yMC4zLTMuM2MtNS41LTEuOC0xMS45IDEuNi0xMS43IDcuNGMuMyA2LjkgMS4zIDEzLjggMy4yIDIwLjdjMTMuNyA1MS4yIDY2LjQgODEuNiAxMTcuNiA2Ny45czgxLjYtNjYuNCA2Ny45LTExNy42Yy0xMS4xLTQxLjUtNDcuOC02OS40LTg4LjYtNzEuMWMtNS44LS4yLTkuMiA2LjEtNy40IDExLjdjMi4xIDYuNCAzLjMgMTMuMiAzLjMgMjAuM3oiLz48L3N2Zz4=";
            toggleIcon.addEventListener("click", function () {
                const passwordInput = document.getElementById("staticrypt-password");
                if (passwordInput.type === "password") {
                    passwordInput.type = "text";
                    toggleIcon.src = imgSrcEyeOpened;
                    toggleIcon.alt = templateToggleAltHide;
                    toggleIcon.title = templateToggleAltHide;
                } else {
                    passwordInput.type = "password";
                    toggleIcon.src = imgSrcEyeClosed;
                    toggleIcon.alt = templateToggleAltShow;
                    toggleIcon.title = templateToggleAltShow;
                }
            });

            // handle password form submission
            document.getElementById("staticrypt-form").addEventListener("submit", async function (e) {
                e.preventDefault();

                const password = document.getElementById("staticrypt-password").value,
                    isRememberChecked = document.getElementById("staticrypt-remember").checked;

                const { isSuccessful } = await staticrypt.handleDecryptionOfPage(password, isRememberChecked);

                if (!isSuccessful) {
                    alert(templateError);
                }
            });
        </script>
    </body>
</html>
