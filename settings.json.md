{
  "workbench.colorCustomizations": null,
  "workbench.colorTheme": "Catppuccin Mocha",
  "window.menuBarVisibility": "toggle",
  "workbench.iconTheme": "material-icon-theme",
  "workbench.list.smoothScrolling": true,
  "editor.smoothScrolling": true,
  "terminal.integrated.smoothScrolling": true,
  "editor.fontFamily": "'JetBrainsMono Nerd Font'",
  "editor.fontSize": 20,
  "editor.accessibilitySupport": "off",
  "workbench.startupEditor": "none",
  
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "[javascript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },

  "code-runner.executorMap": {
    "c": "cd $dir && gcc $fileName -o $fileNameWithoutExt && ./$fileNameWithoutExt",
    "cpp": "cd $dir && g++ $fileName -o $fileNameWithoutExt && ./$fileNameWithoutExt",
    "rust": "cd $dir && rustc $fileName && ./$fileNameWithoutExt"
  },
  "code-runner.runInTerminal": true,
  "code-runner.saveFileBeforeRun": true,
  "code-runner.clearPreviousOutput": true
}
