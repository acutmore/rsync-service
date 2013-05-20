Run AppleScript - service takes folder as input
=============

on run {input, parameters}		set inputFolderA to input	choose folder with prompt "Destination:" without invisibles	set outputFolderA to result	set inputFolder to POSIX path of inputFolderA	set inputFolder to text 1 through -2 of inputFolder	set outputFolder to POSIX path of outputFolderA		tell application "Terminal" to activate	tell application "Terminal"		set newTab to do script		set current settings of newTab to settings set "Pro"		do script "rsync -r -vv " & inputFolder & " " & outputFolder & ";" in newTab	end tell	end run
