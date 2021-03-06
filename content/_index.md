---
title: "CogniCrypt - Secure Integration of Cryptographic Software"
---

A large number of recent studies have shown that most software applications that use cryptographic procedures misuse them in an unsafe manner. The VeraCode Report <a href="https://www.veracode.com/state-software-security-2017" target="_blank">State of the Software Security 2017</a> lists the unsafe use of cryptography as the second most common cause of software vulnerabilities, right after data leakage.

Eclipse CogniCrypt was developed within the collaborative research center CROSSING of  Technische Universität Darmstadt. It allows developers to quickly identify and fix security-critical misuses of crytographic libraries.

The plugin Eclipse CogniCrypt ships in two main components: A wizard for **code generation** that supports a developer in generating secure code for common cryptorgaphic tasks and a **static code analysis** that continuosly checks the (generated and non-generated) code of the developer directly within Eclipse.

![Overview over CogniCrypt](images/home_codegen_codeanalysis.png)

# Code Generation

The Code Generation Feature of CogniCrypt is designed as a wizard that guides developers to select the correct cryptographic algorithms for their cryptographic task at hand. The wizard asks high level questions regarding the task and the data formats the developer needs to encrypt. The [user documentation](./documentation/codegen) discusses the wizard in more detail.

<p align="center">

<video src="videos/codegen.mp4" controls width=800px>
  Ihr Browser kann dieses Video nicht wiedergeben.<br/>
  Dieser Film zeigt eine Demonstration des video-Elements. 
  Sie können ihn unter <a href="#">Link-Addresse</a> abrufen.
</video>

</p>

# Static Code Analysis

The static code analysis feature of CogniCrypt continously checks the developer's code for correct implementations. Upon saving the code in the editor, a static analysis is triggered in the background and reports warning when a cryptographic API is used incorrectly.

The video below shows a minimal example demonstrating the static code analysis within Eclipse.

<p align="center">
<video src="videos/staticanalysis.mp4" controls width=800px>
  Ihr Browser kann dieses Video nicht wiedergeben.<br/>
  Dieser Film zeigt eine Demonstration des video-Elements. 
  Sie können ihn unter <a href="#">Link-Addresse</a> abrufen.
</video> 
</p>
In the Example, the developer creates a `Cipher` object and supplies the `String "AES"` as argument to configure using the encryption algorithm `AES`. They save their code and are warned instantaniously by CogniCrypt. By default, the algorithm `AES` encrypts with the insecure block mode `ECB` and does not use any padding. The developer changes the `Cipher` object to be cofigures in a secure way (using the `String "AES/CBC/PKCS5Padding"` which tells to use a secure block mode `"CBC"` and a correct padding mode). CogniCrrypt's error message disappears. For a more in-depth explanation, please check out the [user documentation](./documentation/codeanalysis).