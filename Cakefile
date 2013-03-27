{spawn, exec} = require "child_process"

# Helpers
# -------

# **`procExec(procName)`**
# returns the path to executable in `node_`
procExec = (procName) -> 
	"./node_modules/.bin/" + procName

# **`processOutput(proc)`**
# handle the output of a `spawn`-ed process
# see **[link](http://stackoverflow.com/a/7376108/292291)**
processOutput = (proc) ->
	proc.stdout.on "data", (data) -> 
		console.log data.toString().trim()

# **`handleOutput(err, output)`**
# handle the output from a `exec`-ed process
handleOutput = (err, output) ->
	if err then throw err
	console.log output

task "startdev", "Start watchers", ->
	# watch and compile Stylus
	stylus = spawn procExec("stylus"), ["./css", "-l", "-w", "-o", "./css"]
	processOutput stylus