
#include <iostream>
#include <map>
using namespace std;

// Define Morse code mappings
map<char, string> morseCode = {
    {'A', ".-"}, {'B', "-..."}, {'C', "-.-."}, {'D', "-.."}, {'E', "."},
    {'F', "..-."}, {'G', "--."}, {'H', "...."}, {'I', ".."}, {'J', ".---"},
    {'K', "-.-"}, {'L', ".-.."}, {'M', "--"}, {'N', "-."}, {'O', "---"},
    {'P', ".--."}, {'Q', "--.-"}, {'R', ".-."}, {'S', "..."}, {'T', "-"},
    {'U', "..-"}, {'V', "...-"}, {'W', ".--"}, {'X', "-..-"}, {'Y', "-.--"},
    {'Z', "--.."}, {' ', " "}  // Preserve spaces between words
};

string translateToMorse(string text) {
    string morse = "";
    for (char c : text) {
        if (morseCode.find(toupper(c)) != morseCode.end()) {
            morse += morseCode[toupper(c)] + " ";
        }
    }
    return morse;
}

int main() {
    string input;
    cout << "Enter text to translate into Morse code: ";
    getline(cin, input);

    cout << "Morse Code Translation: " << translateToMorse(input) << endl;
    return 0;
}
