#include <iostream>
#include <iomanip> // for setw function
#include <limits>  // for cin.ignore and cin.get

using namespace std;

int main() {
    // Define escape codes for colors
    const string resetColor = "\033[0m";
    const string redColor = "\033[31m";
    const string greenColor = "\033[32m";
    const string yellowColor = "\033[33m";
    const string blueColor = "\033[34m";
    const string magentaColor = "\033[35m";
    const string cyanColor = "\033[36m";

    // The title string
    string title = "Quest of the Ancient";

    // Calculate the left padding to center the text
    int padding = (80 - title.length()) / 2; // Assuming the console width is 80 characters

    // Move the title down by printing empty lines
    cout << endl;

    // Print padding for the title
    cout << setw(padding) << "" << std::flush;

    // Print each character with a different color
    for (char c : title) {
        switch (c) {
            case 'Q':
                cout << redColor << c;
                break;
            case 'u':
                cout << greenColor << c;
                break;
            case 'e':
                cout << yellowColor << c;
                break;
            case 's':
                cout << blueColor << c;
                break;
            case 't':
                cout << magentaColor << c;
                break;
            case ' ':
                cout << resetColor << c;
                break;
            default:
                cout << cyanColor << c;
        }
    }

    // Reset color at the end
    cout << resetColor << endl;

    // Print padding for the message
    cout << setw(padding) << "" << "Press Enter to proceed...";
    cin.ignore(numeric_limits<streamsize>::max(), '\n'); // Clear input buffer
    cin.get(); // Wait for Enter key

    return 0;
}
