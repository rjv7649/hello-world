def generateKey(string, key):
    key = list(key)
    if len(string) == len(key):
        return (key)
    else:
        for i in range(len(string) -
                       len(key)):
            key.append(key[i % len(key)])
    return ("".join(key))


# This function returns the
# encrypted text generated
# with the help of the key
def cipherText(string, key):
    cipher_text = []
    for i in range(len(string)):
        x = (ord(string[i]) +
             ord(key[i])) % 26
        x += ord('A')
        cipher_text.append(chr(x))
    return ("".join(cipher_text))


# This function decrypts the
# encrypted text and returns
# the original text
def originalText(cipher_text, key):
    orig_text = []
    for i in range(len(cipher_text)):
        x = (ord(cipher_text[i]) -
             ord(key[i]) + 26) % 26
        x += ord('A')
        orig_text.append(chr(x))
    return ("".join(orig_text))


# Driver code
if __name__ == "__main__":
    kefiley = open('test_key.txt')
    keyword = "KEY"
    file = open('test.txt', 'r')
    for line in file:
        line = line.split()

        for word in line:
            string = word

            key = generateKey(string, keyword)
            tKey = open("test_key.txt", 'a')
            tKey.write("".join(key) + " ")

            cipher_text = cipherText(string, key)
            tE  = open("test_end.txt", 'a')
            tE.write(cipher_text + " ")
        tKey.write("\n")
        tE.write("\n")
    file = open("test_end.txt", 'r')

    for line in file:
        line = line.split()

        for cipher_text in line:
            newKey = open("test_key.txt", 'r')
            for line in newKey:
                line = line.split()
                for word in line:
                    if(len(cipher_text) == len(word)):
                        key = word
                        break


            original_text = originalText(cipher_text, key)
            tD = open("test_dec.txt", 'a')
            tD.write(original_text + " ")
        tD.write("\n")



    string = input("Enter a String: ")
    keyword = input("Enter a keyword: ")
    key = generateKey(string, keyword)
    cipher_text = cipherText(string, key)
    print("Ciphertext :", cipher_text)
    print("Original/Decrypted Text :",
          originalText(cipher_text, key))
