https://github.com/user-attachments/assets/3fce0d2c-1979-4f35-be06-10802533ea3f



# Pyvoice

[![License](https://img.shields.io/pypi/l/pyvoice-language-server)](https://opensource.org/licenses/GPL-3.0)
[![Gitter](https://badges.gitter.im/PythonVoiceCodingPlugin/pyvoice.svg)](https://app.gitter.im/?updated=1.11.31#/room/#pythonvoicecodingpluginpyvoice:gitter.im)
[![PyPI](https://img.shields.io/pypi/v/pyvoice-language-server.svg)](https://pypi.org/project/pyvoice-language-server/)
[![Visual Studio Marketplace](https://img.shields.io/visual-studio-marketplace/v/mpourmpoulis.pyvoice)](https://marketplace.visualstudio.com/items?itemName=mpourmpoulis.pyvoice)


pyvoice is an experimental project that is aimed at developers that are writing python code using their voice instead of/alongside with a traditional keyboard. It attempts to provide them with specialized IDE features tailored at their use case, more specifically, it tries to

- primarily improve the dictation accuracy for coding tasks  by extracting information from the user's codebase via static analysis and utilizing it as context for the speech recognition engine

- secondarily allow for fine-grained, yet more high level editing



![](https://github.com/user-attachments/assets/3fce0d2c-1979-4f35-be06-10802533ea3f)

The project follows a 3 tier architecture

- at its core lies a customized language server, where all the heavy business logic takes place. It employs static analysis to determine what module names are available for importing, what variables and what attributes/methods they have etc..., and generates dictation hints for them. It can also being instructed to perform (for the time being limited) edits

- a plugin for the users code editor, that is responsible for packaging/installing language_server ,launching it as a separate process and to exchange messages with it via appropriate extensions to [LSP](https://microsoft.github.io/language-server-protocol/). It acts as a middleman forwarding generated hints to and commands from the final component of the system, which is


- an add-on/plugin/grammar file for the user's programming by voice system, that customize the system in a manner appropriate to take advantage of the functionality provided by the language server. 



> [!IMPORTANT]
> At this point is important to clarify that pyvoice ***is NOT a standalone voice coding system*** with its own speech recognition engine and/or specialized IDE/GUI environment, that you just download and use independently. 
> Instead, it is meant as a set of extensions that should seamlessly integrate with your existing tooling and augment it with additional functionality.
> At the moment the are grammar bindings available for [Caster](https://github.com/dictation-toolbox/Caster) and [Talon](https://talonvoice.com/), and editorwise plugins for Sublime Text and VsCode

As stated above the project is still highly experimental, essentially having received the absolutely minimum amount of pollishing needed to transit from a tool privately used only by me to something that could be distributed to fellow voice coders. In order to make the time budget for this initial release, corners have been cut everywhere: with features being left out and multiple trade-offs made in all of the five components.


