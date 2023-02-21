# Toggle Stage Manager

Toggle Mac OS Stage Manager on and off.

## Usage

Trigger the Workflow by typing `stage`. Press enter to toggle Stage Manager on and off.

![Screenshot of using toggle stage manager](Workflow/images/usage-screenshot.png)

## Details

Once triggered the Workflow will run the following script in bash:

```bash
STATE=$(defaults read com.apple.WindowManager GloballyEnabled 2> /dev/null)
[[ ${STATE} = 0 ]] && ENABLE="true" || ENABLE="false"
defaults write com.apple.WindowManager GloballyEnabled -bool ${ENABLE}
```

## Credits

Developed by Sam Edwardes. The code snippet is taken from <https://www.reddit.com/r/MacOSBeta/comments/w56e2l/i_made_a_shortcut_to_toggle_macos_venture_stage>.