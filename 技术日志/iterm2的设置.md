##iterm2的设置

    隐藏iTerm Dock 图标 
    让我们的终端变得更 Cool，让它来无影去无踪。这一步我要 iTerm 启动后不再出现在 Dock 上，打开终端输入下面的命令，然后重启 iTerm。

        /usr/libexec/PlistBuddy -c "Add :LSUIElement bool true" /Applications/iTerm.app/Contents/Info.plist
        
    这个方法是通用的，LSUIElement1可控制app 
    以无Dock，无菜单栏的方式运行，另外LSBackgroundOnly2可让 app 以无窗口的方式在后台运行。详细说明可查看 LaunchServicesKeys  
    如果要恢复 Dock 图标：

         
