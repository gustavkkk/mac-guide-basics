### [xcode-select: error: tool 'xcodebuild' requires Xcode, but active developer directory '/Library/Developer/CommandLineTools' is a command line tools instance](https://stackoverflow.com/questions/17980759/xcode-select-active-developer-directory-error/17980786.)

    1. Install Xcode (get it from https://developer.apple.com/xcode/) if you don't have it yet.
    2. Accept the Terms and Conditions.
    3. Ensure Xcode app is in the /Applications directory (NOT /Users/{user}/Applications).
    4. Point xcode-select to the Xcode app Developer directory using the following command:
    $ sudo xcode-select -s /Applications/Xcode.app/Contents/Developer
    Note: Make sure your Xcode app path is correct.
    Xcode: /Applications/Xcode.app/Contents/Developer
    Xcode-beta: /Applications/Xcode-beta.app/Contents/Developer

    
