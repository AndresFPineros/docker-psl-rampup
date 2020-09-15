# Debugging app inside container on runtime #
1. Git clone this ramp up code 
2. cd to this repo parent folder 
3. Build the image with 
`docker build -t learning/csharp:1.0.0  ./c#/ `
4. Run the container: 
`docker run --name "csharp" -v ${pwd}:/work -w /work -p 5000:5000 learning/csharp:1.0.0` 
5. install the c# extension on visual studio code. Go to extensions and search for c#
6. go to the debug tab and clic on add configuration
7. add the following configuration:
```         
{
            "name": ".NET Core Docker Attach",
            "type": "coreclr",
            "request": "attach",
            "processId": "${command:pickRemoteProcess}",
            "pipeTransport": {
                "pipeProgram": "docker",
                "pipeArgs": [ "exec", "-i", "csharp" ],
                "debuggerPath": "/root/vsdbg/vsdbg",
                "pipeCwd": "${workspaceRoot}",
                "quoteArgs": false
            },
            "sourceFileMap": {
                "/work": "${workspaceRoot}/c#/src/"
             }
}
```
8. once the container is running, go to the debug tag and click on the run icon.
9. After this, add a breakpoint in c#/src/Pages/Privacy.cshtml.cs.
10. finally open your broeser in localhost:5000 and clic the privacy button, then check the debugger and you will se its output
