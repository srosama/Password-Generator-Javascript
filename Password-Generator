function generatePassword(passwordLength = 8, IncludeLowerCaseCharters = true, IncludeUpperCaseCharters = true, IncludeSymbols = true, IncludeNumbers = true, ExcludeSimilarCharacters = false, ExcludeAmbiguousCharacters = false) {
    if (![8, 16, 24].includes(passwordLength)) {
        throw new Error("Invalid password length. It should be one of [8, 16, 24].");
    }

    let characters = "";
    if (IncludeLowerCaseCharters) {
        characters += "abcdefghijklmnopqrstuvwxyz";
    }
    if (IncludeUpperCaseCharters) {
        characters += "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
    }
    if (IncludeSymbols) {
        characters += "!\"#$%&'()*+,-./:;<=>?@[\\]^_`{|}~";
    }
    if (IncludeNumbers) {
        characters += "0123456789";
    }

    if (ExcludeSimilarCharacters) {
        characters = characters.replace(/[1lIo0Oo]/g, '');
    }

    if (ExcludeAmbiguousCharacters) {
        characters = characters.replace(/[{}[\]()/\\'"`~,;:.<>]/g, '');
    }

    if (characters.length === 0) {
        throw new Error("No character types selected. Please include at least one character type.");
    }

    let password = "";
    for (let i = 0; i < passwordLength; i++) {
        password += characters.charAt(Math.floor(Math.random() * characters.length));
    }

    return password;
}
