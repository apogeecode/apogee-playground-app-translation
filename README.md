# Translation

## Tools You Will Need

- [VS Code](https://code.visualstudio.com/), or any other text editor/IDE
- [Git](https://git-scm.com/downloads)
- [GitHub Account](https://github.com/)

## Useful Links

- [VS Code Top-Ten Pro Tips](https://www.youtube.com/watch?v=u21W_tfPVrY)
- [VS Code Source Control](https://code.visualstudio.com/docs/editor/versioncontrol)
- [Git Explained in 100 Seconds](https://www.youtube.com/watch?v=hwP7WQkmECE)
- [Git It? How to use Git and Github](https://www.youtube.com/watch?v=HkdAHXoRtos)
- [GitHub Pull Request in 100 Seconds](https://www.youtube.com/watch?v=8lGpZkjnkt4)

## First Time Setup

1. Download and install all the [required tools](#tools-you-will-need)
2. Create a [GitHub](https://github.com/) account, and [enable 2 Factor Authentication](https://docs.github.com/en/authentication/securing-your-account-with-two-factor-authentication-2fa/configuring-two-factor-authentication). You can use [Authy](https://authy.com/) as the 2FA app
3. Contact @recoskyler, and tell him your GitHub username
4. Open VS Code, terminal, or command prompt
5. Enter `git config --global user.name "YOUR FULL NAME"` and `git config --global user.email "YOUR GITHUB EMAIL"` commands, press <kbd>ENTER</kbd> after each command
6. Navigate to the folder where you would like to store the project using `cd FOLDER_NAME` to go in a directory, or `cd ..` to go up a directory
7. Clone the repository using `git clone https://github.com/apogeecode/apogee-playground-app-translation.git` command. It will create a folder named **apogee-playground-app-translation**
8. Navigate into the newly created project folder using `cd apogee-playground-app-translation` command, keep the terminal/command prompt open unless you are using VS Code
9. Switch to the *main* branch using the `git checkout main`
10. Create a new branch with the following format: "*YOUR_NAME-LANGUAGE_NAME-translation*", for example "*atalay-turkish-translation*". Use the command `git checkout -b YOUR_NAME-LANGUAGE_NAME-translation` to create and switch to the new branch
11. Open the folder in VS Code using `code .` command. You can use any other IDE to open this folder as well
12. Create a new file using the following format: **intl_*ISO_639-1_LANGUAGE_CODE*.arb**, such as **intl_en.arb** for English. You can find the language codes [here](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes).
13. Copy the contents of the *intl_en.arb* file to the newly created file
14. Replace the value of "**@@locale**" with the new language code

## Translation of The Text

*.arb* files consist of key/value pairs:

```json
{
  "KEY": "VALUE",
  "TEXT_KEY": "Translated text"
}
```

You can translate all the values except the app name itself. **Keys and commas (,) must NEVER be changed.**

- Make sure you are on your branch using the command `git checkout YOUR_NAME-LANGUAGE_NAME-translation`

### Example

*intl_en.arb*

```json
{
  "@@locale": "en",
  "appName": "Apogee Playground",
  "loginButton": "Submit",
  "name": "Name"
}
```

will be translated to

*intl_tr.arb*

```json
{
  "@@locale": "tr",
  "appName": "Apogee Playground",
  "loginButton": "Devam Et",
  "name": "İsim"
}
```

## Submitting Your Translation

1. **Make sure that the only file you have changed/updated/created is the *.arb* file**, if not please undo the changes to all the other files
2. Open the terminal/command prompt, and make sure you are in the project root (*apogee-playground-app-translation* folder)
3. Enter the `git add intl_LANGUAGE_CODE.arb` command, replace the *intl_LANGUAGE_CODE.arb* with the actual file name
4. Enter the `git commit -m "Translated to LANGUAGE_NAME"` command, replace the *LANGUAGE_NAME* with the language name in English (For example: ~~Türkçe~~ *Turkish*)
5. Enter the `git push` command, git might ask you for your credentials
6. Open [the Pull Requests page of the repository](https://github.com/apogeecode/apogee-playground-app-translation/pulls)
7. Click on the "**New Pull Request**" button
8. Select "*translation*" branch as the "base", and your branch as the "compare"
9. Click on the "**Create Pull Request**" button
