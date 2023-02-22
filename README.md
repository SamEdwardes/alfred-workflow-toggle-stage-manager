# Toggle Stage Manager

Toggle Mac OS [Stage Manager](https://support.apple.com/en-us/HT213315) on and off.

## Usage

Trigger the Workflow by typing `stage`. Press enter to toggle Stage Manager on and off.

![Screenshot of using toggle stage manager](Workflow/images/usage-screenshot.png)

Alternatively, you can trigger the workflow using the **Ctrl-Opt-S** hotkey.

## Details

Once triggered the Workflow will run the following script in bash:

```bash
STATE=$(defaults read com.apple.WindowManager GloballyEnabled 2> /dev/null)
[[ ${STATE} = 0 || -z ${STATE} ]] && ENABLE="true" || ENABLE="false"
defaults write com.apple.WindowManager GloballyEnabled -bool ${ENABLE}
```

## Credits

Developed by Sam Edwardes. The original code snippet is taken from <https://www.reddit.com/r/MacOSBeta/comments/w56e2l/i_made_a_shortcut_to_toggle_macos_venture_stage>.

## Changelog

<https://github.com/SamEdwardes/alfred-workflow-toggle-stage-manager/releases>