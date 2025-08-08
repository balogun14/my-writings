# Debugging a C# Project in Visual Studio Code: A Beginner's Guide

Debugging is an essential skill for any developer. It allows us to identify and fix issues in our code. This guide will walk you through the process of debugging a C# project in Visual Studio Code (VS Code).

## Prerequisites

Before you start, ensure you have the following installed:

1. **Visual Studio Code**: Download and install from [here](https://code.visualstudio.com/).
2. **.NET SDK**: Install the .NET SDK from [here](https://dotnet.microsoft.com/download).
3. **C# Extension for VS Code**: Install the C# extension from the Extensions view in VS Code (`Ctrl+Shift+X` or `Cmd+Shift+X` on macOS) or directly from the [marketplace](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).

## Step 1: Create a Simple C# Project

If you don't already have a C# project, you can create one:

1. Open a terminal in VS Code (`Ctrl+``).
2. Run the following command to create a new console project:

   ```bash
   dotnet new console -n MyFirstCSharpApp
   ```

3. Navigate into the project directory:

   ```bash
   cd MyFirstCSharpApp
   ```

4. Open the project in VS Code:

   ```bash
   code .
   ```

You should now see a simple `Program.cs` file with a `Console.WriteLine("Hello World!")` method.

## Step 2: Set Up Debugging Configuration

All other  things been equal `ceteris paribus`
it is very easy to debug a c# code in vscode 
1. locate the debug icon or press this shortcut `Ctrl+Shift+D`
![[Pasted image 20250118213008.png]]
2. Click Run and debug
![[Pasted image 20250118213236.png]]
3. you should see a modal select c#
![[Pasted image 20250118213349.png]]

4. you will be prompted to select your project
5. it's that easy
## Step 3: Add Breakpoints

Breakpoints allow you to pause the execution of your program at specific lines of code. To add a breakpoint:

1. Open `Program.cs`.
2. Click to the left of the line number where you want to add a breakpoint. A red dot will appear, indicating a breakpoint.
![[Pasted image 20250118213850.png]]

For example:

```csharp

        Console.WriteLine("Hello, World!"); // Set a breakpoint here
```

## Step 4: Start Debugging

Now that everything is set up, you can start debugging:

1. Open the Debug view by clicking on the bug icon in the Activity Bar on the side of the window or by pressing `Ctrl+Shift+D` (`Cmd+Shift+D` on macOS).
2. Select the **".NET Core Launch (console)"** configuration from the dropdown at the top of the Debug view.
3. Click the green **Start Debugging** button (or press `F5`).

The debugger will start, and your program will run until it hits the breakpoint. At that point, execution will pause, and you can inspect variables, step through code, and more.

## Step 5: Inspect Variables and Step Through Code

When the debugger hits a breakpoint, you can:

1. **Inspect Variables**: Hover over a variable to see its current value, or look at the **Variables** section in the Debug view.
2. **Step Over**: Press `F10` to execute the current line and move to the next one.
3. **Step Into**: Press `F11` to step into a method call.
4. **Step Out**: Press `Shift+F11` to step out of the current method.
5. **Continue**: Press `F5` to continue running the program until the next breakpoint or the end of the program.

## Step 6: Using the Debug Console

The Debug Console allows you to interact with your program while it's paused. You can:

1. Evaluate expressions: Type an expression (e.g., `x + 1`) and press `Enter` to see the result.
2. Execute commands: Use commands like `?` to get help or `print x` to print the value of a variable.

## Step 7: Handling Exceptions

If your program throws an exception, the debugger will pause at the line where the exception occurred. You can:

1. Inspect the exception details in the **Call Stack** or **Variables** section.
2. Use the **Continue** button (`F5`) to resume execution if you've handled the exception.

## Step 8: Stopping the Debugger

To stop debugging:

1. Click the red **Stop** button in the Debug view.
2. Alternatively, press `Shift+F5`.

 # Advanced
  VS Code uses a `launch.json` file to configure debugging. Let's create one:

1. Open the Command Palette (`Ctrl+Shift+P` or `Cmd+Shift+P` on macOS).
2. Type and select **"Debug: Open launch.json"**.
3. Choose **".NET Core"** from the list of environments.

This will generate a `launch.json` file in the `.vscode` folder. It should look something like this:

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": ".NET Core Launch (console)",
      "type": "coreclr",
      "request": "launch",
      "preLaunchTask": "build",
      "program": "${workspaceFolder}/bin/Debug/net8.0/MyFirstCSharpApp.dll",
      "args": [],
      "cwd": "${workspaceFolder}",
      "console": "internalConsole",
      "stopAtEntry": false
    }
  ]
}
```

This configuration tells VS Code how to launch and debug your C# application.

## Tips for Effective Debugging

1. **Use Multiple Breakpoints**: Place breakpoints at different points in your code to understand the flow of execution.
2. **Watch Expressions**: Add expressions to the **Watch** section to monitor their values as you step through the code.
3. **Logging**: Use `Console.WriteLine` or a logging framework like serilog to output information to the console, which can help you understand what's happening without pausing execution.

## Conclusion

Debugging is a powerful tool that helps you understand and fix issues in your code. By following this guide, you should now be able to set up and use the debugger in Visual Studio Code for your C# projects. As you gain more experience, you'll discover additional features and techniques that can make debugging even more efficient.

Happy coding! 🚀
Jaiye Lo