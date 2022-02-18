# Obfuscated Application

### Description

A Web Api project that has been obfuscated

### Dependencies:

* Dotnet Peak - used to decompile dll's and view code

### Obfuscate Application

* Build application in both Debug and Release mode.
	* Open the Debug dll of ObfuscatedApplication.dll, you will notice that the Debug dll has all our comments and looks very much like the original code. This is because the dll was build along with a pdb file.
	* Open the Release dll of ObfuscatedApplication.dll, you will notice is it different to the Debug dll, comments have been removed and additional code has been added. This is because the dll does not contain a pdb file and 	the code has been optomized.
* Using the Release dll, run it through "Dotnet Reactor" which will obfuscate the code even further.
	* Turn the following settings on in Dotnet Reactor:
		* NecroBit: stops decompiling of dll.
		* Anti ILDASM: suppresses decompilation using decompilation tools.
		* Anti Tampering: prevents assembly from being tampered with
		* Anti Debug: prevents debugging of the process. The application will terminate if process is attached too.
		* Control Flow obfuscation: scrammbles the code so it is hard to read by renaming classes, properties and methods etc. as well as moving code around while keeping the order of execution of code intact.
		* Compress & Encrypt Resources: compresses and encrypts resources.
* A folder (ObfuscatedApplication_Secure) in the same directory as the selected dll should have been created with the obfuscated dll.
* One should be carefull with obfuscating code as it could cause reflection code to break.
* Also, there is a performance hit because of code being scrabbled. Obfuscating your code adds a lot of redirects (goto statements) in your code.
* There are many obfuscation tools (https://github.com/NotPrab/.NET-Obfuscator) out there but one should be carefull as majority of them cause bugs in your application. Dotnet Reactor seems to be the most popular obfuscation tool out there.


### References

* Nick Chapsas: https://www.youtube.com/watch?v=tRHOBV31BeU
* Dotnet Reactor (Obfuscator application): https://www.eziriz.com/dotnet_reactor.htm
* Obfuscation Tools: 
	* https://github.com/NotPrab/.NET-Obfuscator
	* https://blog.ndepend.com/in-the-jungle-of-net-obfuscator-tools/
