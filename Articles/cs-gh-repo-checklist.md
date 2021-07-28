# GitHub Repository Checklist (C#)

Have a repository on GitHub? Planning on making a repository on GitHub? This checklist is intended to introduce you to various features that may help you make the most of your GitHub repository with specific recommendations for C# repsoitories.

## Checklist

<details>
<summary>
Are you happy with the current URL (account, name, default branch)?
</summary>
<p>

> Make sure you are happy with the name of your repo and the account your repo is under. You can rename and transer ownership of repositories, but that will change the URL of your repo, which may cause confusion for your community.
>
> GitHub has organization accounts, so if you already have a group of dedicated developers or intend to grow a community around the repository, having the repository be under an organization's account may be more appropriate than a personal account.<br/>
> [See more information on GitHub organization here.](https://docs.github.com/en/organizations/collaborating-with-groups-in-organizations/about-organizations)
>
> Also, make sure you are happy with the name of your default branch. `"master"` has been a common name for default branches, but most repositories are using `"main"` now. Changing branch names in GitHub is very easy, but it is still easier to start out with your prefered default branch name rather than having to change to it.<br/>
[Here is GitHub's documentation on changing branch names.](https://github.com/github/renaming)

</p>
</details>

<details>
<summary>
Do you have a <code>LICENSE</code>?
</summary>
<p>

> If you don't already have one, you should add a `LICENSE` file to the root of your repository.<br/>
> [See GitHub's guide on licensing here.](https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/creating-a-repository-on-github/licensing-a-repository)

</p>
</details>

<details>
<summary>
Do you have a <code>.gitignore</code>?
</summary>
<p>

> Don't include unnecessary content in your repository. Your repository should include the source code for your project. It should not include compilation results (the `bin` and `obj` folders), compiler generated `.xml` files, user-specific IDE settings (such as the `.vs` directory created by Visual Studio), etc. The binaries (compilation results) belong in releases and/or packages rather than the files of your repository.
>
> The `.gitignore` file is how you can control what files are included or excluded from your repository. For C# repsoitories, if you use GitHub's online interface, you want to choose the `Visual Studio` option when you create your repository:
>
> ![image](https://user-images.githubusercontent.com/3385986/126922682-eee60260-8cb8-473e-8808-bce382db40c3.png)
>
> If you need to add or update a `.gitignore` file to an existing repsoitory, you copy the latest version of the `Visual Studio` template here:
> [https://github.com/github/gitignore/blob/master/VisualStudio.gitignore](https://github.com/github/gitignore/blob/master/VisualStudio.gitignore)
>
> [See git's documentation on `.gitignore` here.](https://git-scm.com/docs/gitignore)

</p>
</details>

<details>
<summary>
Do you have a <code>.gitattributes</code>?
</summary>
<p>

> `.gitattributes` is a settings file for `git`. The most common use is to standardize line endings, so that when the code is cloned it will have the appropriate line endings based on the environment from which is is cloned. For C# repositories, you generally just want to use this as your `.gitattributes`:
> ```
> * text=auto
> ```
> However, if you do have any binary files you should add explicit entries for those types of files to make sure they do not get corrupted. For example, if you have a `.png` image file in your repository you could add this line to your `.gitattributes`:
> ```
> *.png binary
> ```
>
> > `.gitattributes` files can especially help if you have content that requires specific line endings such as shell scripts.
>
> [See git's documentation on `.gitattributes` here.](https://git-scm.com/docs/gitattributes)

</p>
</details>

<details>
<summary>
Do you have a <code>README.md</code>?
</summary>
<p>

> If you don't already have one, you should add a `README.md` file to the root of your repository. GitHub will show the contents of the `README.md` file located in the current directory without users having to open that file explicitily. So, if you have a `README.md` in the root of your project, GitHub will show that content on the landing page of your repository. If you put a `README.md` file in a sudirectory like `Test A/Test B/README.md`, than the content of that file will be shown by GitHub when a user accesses the `Test A/Test B/` directory.
>
> GitHub supports other formats for `README` files such as `.txt`, but markdown `.md` is the prefered format as it supports formatting features other formats do not.<br/>
> [Here is GitHub's documentation on markdown.](https://guides.github.com/features/mastering-markdown/)

</p>
</details>

<details>
<summary>
Do you have a <code>.editorconfig</code>?
</summary>
<p>

> An `.editorconfig` file is a settings file supported by most common C# IDEs and editors. It includes settings like tabs vs spaces, indentation size, suppressing compiler warnings, and more. You can have multiple `.editorconfig` files in various directories if you need directory specific settings.
>
> [Here is `.editorconfig` infromation on `https://docs.microsoft.com/`.](https://docs.microsoft.com/en-us/visualstudio/ide/create-portable-custom-editor-options)
>
> [Here is `.editorconfig` infromation on `https://editorconfig.org/`.](https://editorconfig.org/)
>
> [Here is the `.editorconfig` plugin for `Visual Studio Code`.](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig)

</p>
</details>

<details>
<summary>
Do you have "<code>dotnet test</code>" projects?
</summary>
<p>

> If you don't already have a unit testing project, consider making one. Unit tests help with regression testing, validate code works on different environments, doing test-driven development, etc. Unit tests can also serve as examples of how to use the code.
>
> Unit testing projects are seperate projects from your source code (you should have multiple `.csproj` files in different directories). Unit tests can be run with the `dotnet test` command. There are several popular frameworks for unit testing: `MSTest`, `NUnit`, and `XUnit`. While there are minor feature differences between them, they can all get the job done.
>
> > Note: it is fairly common for new .NET developers to implement unit testing as a console application rather than using a "`dotnet test`" supported framework. You should really use a "`dotnet test`" supported framework.
>
> [More information here. (unit testing guide)](https://docs.microsoft.com/en-us/visualstudio/test/walkthrough-creating-and-running-unit-tests-for-managed-code)
>
> [More information here. (`dotnet test`)](https://docs.microsoft.com/en-us/dotnet/core/tools/dotnet-test)

</p>
</details>

<details>
<summary>
Do you have unit testing code coverage on your <code>README.md</code>?
</summary>
<p>

> Have you seen a badge like this on other repositories?<br/>
> ![codecov-badge](https://raw.githubusercontent.com/ZacharyPatten/ZacharyPatten/main/Resources/github-repo-checklist/codcov-badge.svg)
>
> That percentage represent how much of the source code is touched by unit tests. Generally, the higher the percentage of your code that is unit tested, the more robust/reliable your code is.
>
> > Note: Try to write meaningful unit tests rather than slapping on unit tests to achieve 100% coverage. Just because you have a high coverage percentage does not mean your code is bug free. Having unreliable, excessive, or verbose unit testing can sometimes hinder a project more than help it.
>
> How to I get my test coverage?
>
> [More information here (MS Docs code coverage).](https://docs.microsoft.com/en-us/dotnet/core/testing/unit-testing-code-coverage)
>
> Here are some common resources for producing code coverage reports:
>
> - `CodeCov`: [https://about.codecov.io/](https://about.codecov.io/)
> - `SonarCloud`: [https://sonarcloud.io/](https://sonarcloud.io/)
> - `ReportGenerator`: [https://github.com/danielpalme/ReportGenerator](https://github.com/danielpalme/ReportGenerator)

</p>
</details>

<details>
<summary>
Are your .NET target(s) on your <code>README.md</code>?
</summary>
<p>

> It is important to clearly display the .NET target(s) of your project on your landing page. Are you targetting `.NET 5`, `.NET 6`, `.NET Standard 2.0`, `.NET Framework 4.8`, or any other version? You don't want to make your community dig through your `.csproj` files or try to run your application only to find out it is dependent on `.NET 9000` which they don't have installed yet.
>
> This could be as simple as including a comment at the top of your `README.md` file:
>
> > This project targets [.NET 5](https://dotnet.microsoft.com/download).
>
> But an nicer way is to just make a badge. You can even make the badge dynamic so that if you change your .NET target (such as migrating from `.NET 5` to `.NET 6`) the badge can automatically update for you. Here is an example of a .NET target badge:<br/>
> <a href="https://dotnet.microsoft.com/download" alt=".NET target"><img alt=".NET target" src="https://img.shields.io/badge/dynamic/xml?color=%23512bd4&label=target&query=%2F%2FTargetFramework%5B1%5D&url=https%3A%2F%2Fraw.githubusercontent.com%2FZacharyPatten%2FTowel%2Fmain%2FSources%2FTowel%2FTowel.csproj&logo=.net" title="Go To .NET Download"></a>
>
> [Here is a guide on how you can set up a dynamic .NET target badge for your repository.](https://github.com/ZacharyPatten/ZacharyPatten/blob/main/Articles/2020-09-12.md)

</p>
</details>

<details>
<summary>
Are your recommended <code>build processes</code> and <code>IDEs</code> on your <code>README.md</code>?
</summary>
<p>

> If you have any custom build processes, such as `.cmd` scripts like "`Build.cmd`" or "`Restore.cmd`", put it on your root `README.md`. Don't burry it on another page (such as a `Wiki` page) that new users may miss upon first glance.
>
> Also put what `IDEs` you project supports on your `README.md`:
>
> - Visual Studio?
> - JetBrains Rider?
> - Visual Studio Code? _(see the `.vscode/xxx.json` bullet below)_
> - Visual Studio for Mac?
> - other?
>
> If you have a Windows Forms Application, then 
>
> Here are some badges you can copy 
>
> _todo_
  
</p>
</details>

<details>
<summary>
Do you have <code>.github/workflows/xxx.yml</code> files (workflows)?
</summary>
<p>

> The `.github/workflows/` directory is where you define workflows. Workflows can do a lot of things for you

</p>
</details>

<details>
<summary>
Are <code>Issues</code> and/or <code>Discussions</code> enabled on your repository?
</summary>
<p>

> `Issues` and `Discussions` are two seperate features on GitHub. `Issues` is enabled on GitHub repositories by default, but `Discussions` is not. You can enable or disable either feature from the settings of your repository. `Discussions` is a newer feature and is currently considered to be in a `beta` version.
>
> For a C# repository, it is likely a good idea to have both `Issues` and `Discussions` enabled. `Issues` are a great place to track bugs and feature requests. `Discussions` are generally a better place to have conversations, such as users asking questions or showcasing projects. `Discussions` allow users to reply to other comments while in `Issues` users can only reply to the original post.
>
> [More information here. (GitHub `Issues`)](https://guides.github.com/features/issues/)
>
> [More information here. (GitHub `Discussions`)](https://docs.github.com/en/discussions)

</p>
</details>

<details>
<summary>
Do you have clearly defined <code>Labels</code> for issues?
</summary>
<p>

> `Labels` help you categorize and document `Issues`.
>
> [More information here.](https://docs.github.com/en/issues/using-labels-and-milestones-to-track-work/managing-labels)

</p>
</details>

<details>
<summary>
Do you have <code>Milestones</code> and/or <code>Projects</code> for issues?
</summary>
<p>

> &bull; `Milestones`
>
> `Issues` are great for documenting bugs an enhancements, but how do you document the the timelines/deadlines of them? That is where `Milestones` can help. If you are planning on a future release `3.0.0` it may be nice to create a milestone for that release, and put the relevant issues inside that milestone. That way your community can clearly see what all issues still need to be addressed for the upcoming `3.0.0` release.
>
> `Milestones` are built into `Issues` and thus are enabled if `Issues` are enabled.
>
> [More information here.](https://docs.github.com/en/issues/using-labels-and-milestones-to-track-work/about-milestones)
>
> &bull; `Projects`
>
> `Projects` is a seperate feature from `Issues` and can be enabled/disabled in the settings of the repository. `Projects` are enabled by default.
>
> `Projects` are an additional way to categorize and track `Issues`. While `Milesteones` are useful, they don't necessarily track the state of an `Issue` (has work on the `Issue` started or not). `Projects` are intended to fill in that need.
>
> [More information here (GitHub about project boards).](https://docs.github.com/en/issues/organizing-your-work-with-project-boards/managing-project-boards/about-project-boards)

</p>
</details>

<details>
<summary>
Do you have<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&bull; <code>Issues</code> templates,<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&bull; a <code>.github/ISSUE_TEMPLATE/config.yml</code>,<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&bull; and a <code>.github/pull_request_template.md</code> (pull request template)?
</summary>
<p>

> &bull; `Issues` templates
>
> You can set up issue templates so that when creating a new issue, users can select from templates you make. `Bug` and `Enhancement` are common templates for example. With the templates, you can pre-populate issues with content such as labeling issues.
> [More information here.](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/about-issue-and-pull-request-templates)
>
> &bull; `.github/ISSUE_TEMPLATE/config.yml`
>
> When creating new GitHub `Issues` on your repository, the `.github/ISSUE_TEMPLATE/config.yml` file will let you add options that link to other locations. For example, you may want to direct questions to be opened as `Discussions` rather than `Issues`, or if you have multiple repositories you may want to have a message like `If your issue involves XXX please open an issue here instead...`.
> [More information here.](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/configuring-issue-templates-for-your-repository#configuring-the-template-chooser)
>
> &bull; `.github/pull_request_template.md`
>
> When a pull request is opened, GitHub prepopulates the content of the pull request with the `.github/pull_request_template.md` file. This allows you to instruct the community on how you expect pull requests to be written.
> [More information here.](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/creating-a-pull-request-template-for-your-repository)

</p>
</details>

<details>
<summary>
Do you have packages (preferably <code>NuGet</code>)?
</summary>
<p>

> If you are making a library in which you intend for other developers to use your code as a dependency, you should be using packages.
>
> GitHub has package hosting, but most .NET developers use `nuget.org` for hosting packages rather than GitHub, because `nuget.org` is the default source of the `NuGet Package Explorer` in `Visual Studio` when users search for packages.
>
> [More information here (`dotnet pack`).](https://docs.microsoft.com/en-us/nuget/create-packages/creating-a-package-dotnet-cli)
>
> [More information here (publishing NuGet packages).](https://docs.microsoft.com/en-us/nuget/nuget-org/publish-a-package)
>
> [More information here (GitHub `Packages`)](https://github.com/features/packages)
>
> > Note: a great way to handle the creation and deployment of `NuGet` packages is to make a GitHub `Action` that triggers when you publish a `Release` on your repository. Here is an example GitHub `Action`:<br/>[https://github.com/ZacharyPatten/Towel/blob/main/.github/workflows/Towel%20Deployment.yml](https://github.com/ZacharyPatten/Towel/blob/main/.github/workflows/Towel%20Deployment.yml)

</p>
</details>

<details>
<summary>
Are you using GitHub <code>Pages</code>?
</summary>
<p>

> You can host static websites on GitHub for free. The feature is called GitHub `Pages`.<br/>
> [More information here.](https://pages.github.com/)
>
> > Note: GitHub Pages can host `Blazor webassembly` projects.
>
> > Note: GitHub Pages can host documentation generator output like `docfx`. _(see the "documentation generation" bullet below)_

</p>
</details>

<details>
<summary>
Do you have documentation generation (such as <code>docfx</code>)?
</summary>
<p>

> For C# (or any .NET) repositories, there are tools for generating static documentation websites. One of the most popular tools is `docfx`. You can use `docfx` to generate a documenation website, and you have host the generated website on GitHub `Pages` for free. Here are key features of `docfx`:
>
> - it will generate an api reference using the `xml` comments on your source code
> - supports articles in markdown format
> - is easy to customizable (including custom stylings)
> - is easy to include in GitHub `Actions` so it can automatically trigger when you push changes
>
> Here is an example output of `docfx`:<br/>
> [https://zacharypatten.github.io/Towel/api/index.html](https://zacharypatten.github.io/Towel/api/index.html)
>
> Here is an example of a GitHub `Action` that runs `docfx` and deploys it to GitHub `Pages` on code pushes:<br/>
> [https://github.com/ZacharyPatten/Towel/blob/main/.github/workflows/Documentation.yml](https://github.com/ZacharyPatten/Towel/blob/main/.github/workflows/Documentation.yml)
>
> [More information here (`docfx` github repository).](https://github.com/dotnet/docfx)
>
> [More information here (`docfx` tutorial).](https://dotnet.github.io/docfx/tutorial/docfx_getting_started.html)

</p>
</details>

<details>
<summary>
Do you have a <code>change log</code>?
</summary>
<p>

> Your community can see your code changes in the `git` history, but having a summarized change log is really important. Not only is this useful for communities to check what the changes are between versions, it is also useful for potential new contributors by detailing what topics are undergoing active development.
>
> Handle your change log however you want (a `Changelog.md` markdown file in your repository, a page on your wiki, etc.). However, probably the best place to keep your change log is the `Releases` of your GitHub repository. Here ar some examples of change logs implemented in the `Releases` of several GitHub repositories:
>
> - [https://github.com/ZacharyPatten/Towel/releases](https://github.com/ZacharyPatten/Towel/releases)
> - [https://github.com/dotnet/Silk.NET/releases](https://github.com/dotnet/Silk.NET/releases)
> - [https://github.com/Singulink/Singulink.Numerics.BigDecimal/releases](https://github.com/Singulink/Singulink.Numerics.BigDecimal/releases)
>
> > Note: if you have `NuGet` packages, you can just link the release notes on the `NuGet` package back to your GitHub `Releases`, so that you only have one location you need to update. Having to update change logs in mutiple locations can be a pain. Here is an example:<br/>[https://www.nuget.org/packages/Towel/1.0.32](https://www.nuget.org/packages/Towel/1.0.32)<br/>Notice that the "Release Notes" is a link back to the `Release` in GitHub:<br/>
> > ```
> > See https://github.com/ZacharyPatten/Towel/releases/tag/1.0.32
> > ```
> > That way there is only one change log that needs to be updated if there are typos or formatting errors.

</p>
</details>

<details>
<summary>
Do you have <code>branch policies</code>?
</summary>
<p>

> You can protect important branches by setting branch protection rules, which define whether collaborators can delete or force push to the branch and set requirements for any pushes to the branch, such as passing status checks or a linear commit history.
>
> [More information here.](https://docs.github.com/en/github/administering-a-repository/defining-the-mergeability-of-pull-requests/about-protected-branches)

</p>
</details>

<details>
<summary>
Do you have a chat location (possibly an alternate platform than GitHub)?
</summary>
<p>

> GitHub is a great platform for what it does well, but one thing that it does not do very well is acting as a community chat. GitHub `Issues` and `Discussions` are not really intended to be real-time chat platforms. They are relatively slow, they notify everyone who is watching the repository, and they are intended to be permanently retained for future reference.
>
> So, it can be nice to use a platform outside of GitHub where your community can have more laid-back discussions. Use whatever platform you prefer Discord, Gitter, Facebook, Reddit, etc. However Discord gets a special recommendation as it supports multiple channels, text and voice channels, it allows streaming, it supports bots, it support webhooks, it supports custom user roles and permissions, and much more.
>
> If you do set up another platform for your community, clearly document that on your root `README.md` so your community can find it, such as having a badge. Here is an example of a badge for a Discord server:<br/>
<a href="https://discord.gg/4XbQbwF"><img src="https://img.shields.io/discord/557244925712924684?logo=discord&logoColor=ffffff&color=7389D8" title="Go To Discord Server" /></a><br/>
> Here is the markdwon/HTML for that badge:
> ```html
> <a href="https://discord.gg/4XbQbwF"><img src="https://img.shields.io/discord/557244925712924684?logo=discord&logoColor=ffffff&color=7389D8" title="Go To Discord Server" /></a>
> ```

</p>
</details>

<details>
<summary>
Do you have a logo?
</summary>
<p>

> Is a logo required? No, but logos help the community remember your project and associate it with content outside your GitHub repsoitory:
>
> - website
> - social media posts
> - discord, gitter, and other platforms
> - articles
>
> Scalable Vector Graphics (`.svg`) is generally the prefered format for logos, because vector formats will render cleanly on any resolution, unlike raster graphics formats such as `.jpg`, `.png`, `.gif`, `.tif`, etc.
>
> However, if you plan on having nuget packages, nuget currently does not support `.svg` formats. You should still make your logo in the `.svg` format if you can, but you just need to convert it to a raster format (generally `.png`) in order to use it with nuget packages.
>
> Scalable Vector Graphics (`.svg`) support animations. So if you want an animated logo, you can do that with the `.svg` file format. Here is an example:
>
> _todo_

</p>
</details>

<details>
<summary>
Do you have <code>.vscode/xxx.json</code> files?
</summary>
<p>

> Most .NET developers expect to use `Visual Studio`, but `Visual Studio Code` is gaining popularity too. If your project is compatible with `Visual Studio Code` consider adding the following files so `Visual Studio Code` users have an easier time with your repository:
>
> - `.vscode/extensions.json`<br/>This file lets you recommend extensions to users that open your repository in `Visual Studio Code`.<br/>
[More information here.](https://code.visualstudio.com/docs/editor/extension-marketplace#_workspace-recommended-extensions)
> - `.vscode/settings.json`<br/>This is a settings file: enable semantic highlighting, exclude directories from the Explorer, show parameter hints, etc.<br/>[More information here.](https://code.visualstudio.com/docs/getstarted/settings)
> - `.vscode/tasks.json`<br/>This file defines tasks that can be run in Visual Studio Code, such as building your project. Tasks are often referenced from the `launch.json` file.<br/>
[More information here.](https://code.visualstudio.com/docs/editor/tasks)
> - `.vscode/launch.json`<br/>This file defines the options the users can select from the "Run and Debug" view in Visual Studio Code.<br/>
[More information here.](https://code.visualstudio.com/docs/editor/debugging)

</p>
</details>

<details>
<summary>
Do you have a <code>.markdownlint.json</code>?
</summary>
<p>

> [markdownlint](https://github.com/DavidAnson/markdownlint) is a style checker for markdown files. It is supported by various markdown editors and is easy to integrate into pipelines such as [GitHub Actions](https://github.com/features/actions).
>
> `.markdownlint.json` is a settings file used by [markdownlint](https://github.com/DavidAnson/markdownlint) when validating markdown (`.md`) files. For example, by default [markdownlint](https://github.com/DavidAnson/markdownlint) will report errors if inline HTML is used in markdown, but if you want to allow inline HTML the `.markdownlint.json` file can be used to suppress the `MD033 no-inline-html - Inline HTML` errors.
>
> Even if you do not use [markdownlint](https://github.com/DavidAnson/markdownlint), members of your community might (such as the extension for `Visual Studio Code`), and if they open your markdown files they may see a lot of notifications if you do not include a `.markdownlint.json` with suppressions.
>
> [Here is the `markdownlint` extension for Visual Studio Code.](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)

</p>
</details>

<details>
<summary>
Do you have a <em>"using my project"</em> badge?
</summary>
<p>

> If you are making a project that is intended to be used by other developers such as a code library, consider making a badge that other developers can easily copy and display on their projects.

</p>
</details>

<details>
<summary>
Do you have GitHub <code>Sponsors</code> set up (community financial support)?
</summary>
<p>

> Have you seen other projects with the "Sponsor" button at the top of their repsoitory? Are you wanting the same for your repository? That feature is simply called HitHub `Sponsors`. You can also configure the sponsor button to link to alternate funding platforms like `Patreon`, `Buy Me a Coffee`, etc.

</p>
</details>

<details>
<summary>
Disable GitHub <code>Wikis</code>?
</summary>
<p>

> Can GitHub `Wikis` be useful? Yes. However, they are often not the best place to put documentation, especially for .NET projects.
>
> - If you are going to use `Wikis`, don't let `Wikis` get verbose. The extra real estate that `Wikis` provide often lead to bloat verbage. No one likes unnecessary filler content. Also don't spread the information too thin. A handful of more dense pages are often preferred to dozens of pages with very little content in them.
> - Often times `Wiki` content could just be put on the root `README.md` rather than distributed among dozens of seperate (often barren) pages in a `Wiki`. Expanders are especially useful so that your `README.md` has a lot of content but is not overwhelming at first glance.
> - If you are using GitHub `Pages` (website), why not just include your documentation on there rather than on a GitHub `Wiki`? Having documentation in multiple places will just cause confusion. Especially if you are using a documentation generator like `docfx`, then you should probably just put on your documentation in your `docfx` content rather than a GitHub `Wiki`. No reason to have both.
> - You can just include markdown files in your repository rather than using the GitHub `Wikis`. This makes it easier to add markdown linting (validation), it will be easier for the community to contribute to, there will only be one history (rather than Wiki + Repository history), and users who clone the repo will have the documentation even if they are offline (without having to had clone the `Wiki` too).
>
> `Wikis` are one of the few features in GitHub that might just be better to ignore/disable. You can enable/disable `Wikis` in the settings of your repository.

</p>
</details>

<details>
<summary>
If you have benchmarking, are you using <code>BenchmarkDotNet</code>?
</summary>
<p>

> Writing a console application using `Stopwatch` or `DateTime` is not a reliable way to gather benchmarking data. If you want to include benchmarking in your repository, you should be using the `benchmarkdotnet`. `benchmarkdotnet` outputs results in a format that is supported by GitHub markdown (you can copy-paste the results directly into GitHub markdown).
>
> [More information here (`benchmarkdotet` github repo).](https://github.com/dotnet/BenchmarkDotNet)

</p>
</details>

<details>
<summary>
If you are using <code>dotnet test</code> with GitHub <code>Actions</code>, are you using <code>Tyrrrz/GitHubActionsTestLogger</code> for cleaner output?
</summary>
<p>

> [More information here (Tyrrrz/GitHubActionsTestLogger GitHub repository).](https://github.com/Tyrrrz/GitHubActionsTestLogger)

</p>
</details>

<details>
<summary>
Do you have a <code>CODE_OF_CONDUCT.md</code>?
</summary>
<p>

> If you want to have a file detailing the code of conduct you expect out of your community, the best place to document that is in a `CODE_OF_CONDUCT.md` file in the root of your repository. That is just the file path/name recommended by GitHub, and many repositories follow that convention, so if you also put for community guidelines in the same file `CODE_OF_CONDUCT.md` it will be easier for your community to find it.

</p>
</details>

<details>
<summary>
Do you have a <code>CONTRIBUTING.md</code>?
</summary>
<p>

> GitHub recommends you make a `CONTRIBUTING.md` file in the root of your repository that documents how your community can contribute to your project. If you write similar documentation you shoudl likely put it in that file name/path so it is easy for your community to find it.

</p>
</details>

<details>
<summary>
Are you using GitHub <code>Topics</code>?
</summary>
<p>

> You can label your repository with various topics, which can make it easier for users to find your repository when searching/exploring GitHub.
>
> <image src="https://user-images.githubusercontent.com/3385986/127240330-8a1b34e0-6656-49c5-ab43-bd2d58456357.png" height="300" />
>
> Then your repository will appear in the search results on pages like [https://github.com/topics](https://github.com/topics).

</p>
</details>

## Tips & Tricks

<details>
<summary>
Use <code>&lt;br/&gt;</code> for line breaks in GitHub markdown.
</summary>
<p>

> If<br/>
> you<br/>
> need<br/>
> a<br/>
> line<br/>
> break<br/>
> use<br/>
> `<br/>`.

</p>
</details>

<details>
<summary>
Use <code>shields.io</code> to make badges.
</summary>
<p>

> [shields.io](https://shields.io/) is a great website you can use to make badges. The badges are in `.svg` file formats and are easy to customize if needed such as adding custom logos.

</p>
</details>

<details>
<summary>
Use expanders in GitHub markdown.
</summary>
<p>

> You can make drop downs on markdown with the following:
> ```html
> <details>
> <summary>
> HEADING
> </summary>
> <p>
> 
> CONTENT
> 
> </p>
> </details>
> ```

</p>
</details>

<details>
<summary>
Use <code>&lt;sub&gt;</code> to <em>nearly</em> vertically center badges and images with text in GitHub markdown.
</summary>
<p>

> Unfortunately there is no way to vertically center badges and images with text in GitHub's markdown. Badges and images are rendered slightly above the midline of the text. However, you can force the badges and images to be slightly lower by wrapping them in `<sub>` tags (which is subscript).
>
> Without `<sub>`: <a href="https://dotnet.microsoft.com/download" alt=".NET target"><img alt=".NET target" src="https://img.shields.io/badge/dynamic/xml?color=%23512bd4&label=target&query=%2F%2FTargetFramework%5B1%5D&url=https%3A%2F%2Fraw.githubusercontent.com%2FZacharyPatten%2FTowel%2Fmain%2FSources%2FTowel%2FTowel.csproj&logo=.net" title="Go To .NET Download"></a>
>
> With~~out~~ `<sub>`: <sub><a href="https://dotnet.microsoft.com/download" alt=".NET target"><img alt=".NET target" src="https://img.shields.io/badge/dynamic/xml?color=%23512bd4&label=target&query=%2F%2FTargetFramework%5B1%5D&url=https%3A%2F%2Fraw.githubusercontent.com%2FZacharyPatten%2FTowel%2Fmain%2FSources%2FTowel%2FTowel.csproj&logo=.net" title="Go To .NET Download"></a></sub>

</p>
</details>

<details>
<summary>
Use <code>&lt;p align="center"&gt;</code> to horizontally center content in GitHub markdown.
</summary>
<p>

> You can horizontally center content in GitHub markdown with the following:
> ```html
> <p align="center">
>     CONTNET
> </p>
> ```
> This is particularly nice for logos and badges.
>
> > Note: you can't mix normal markdwon syntax with inline HTML syntax. So rather than using markdown images like `![IMAGE](SOURCE)` you need to use HTML like `<a href="LINK"><img src="SOURCE"/></a>`.

</p>
</details>

<details>
<summary>
Use <code>&lt;a href="#"&gt;</code> to help prevent image links.
</summary>
<p>

> Unfortunately in GitHub's markdown, there is no way to prevent an image from being a click-able link. GitHub adds links to images and `<a>` tags that wrap images. This is a problem in multiple scenarios such as when you want an image to be in the `<summary>` of a expander (clicking the `<summary>` should toggle the exander rather than being a link). The best thing you can currently do is wrap images with `<a href="#">IMAGE</a>` and then at least they will link to the current page rather opening the URL of the image.

</p>
</details>

<details>
<summary>
:tada: GitHub markdown has emojis.
</summary>
<p>

> :bowtie:<br/>
> :page_facing_up:<br/>
> :file_folder:<br/>
> :meat_on_bone:<br/>
> [See this link.](https://gist.github.com/rxaviers/7360908)
>
> > Note: emojis are especially useful inside of expanders, since images and expanders in GitHum markdown do not play well.

</p>
</details>

<details>
<summary>
GitHub's icons are open source.
</summary>
<p>

> GitHub's icons are open source so you can use them in your content.
> [https://github.com/primer/octicons](https://github.com/primer/octicons)

</p>
</details>

<details>
<summary>
Links to GitHub queries.
</summary>
<p>

> You can create links to queries in GitHub. One use case for this could be linking to all Q/A discussions that haev not yet been answered so you can make sure they get help quickly.
>
> Here is the base URL you want to use: `https://github.com/search`
>
> > Note: avoid using other base URLs like `https://github.com/issues`, because those are only accessible by users who are logged into their GitHub. `https://github.com/search` works even for users who are not logged into GitHub.
>
> Then you can add parameters such as `q=author%3Azacharypatten` and to `is%3Aissue+is%3Aopen` adjust the resulting query of the link. For example this link results in a query of all `Issues` opened by the user `zacharypatten`:<br/>
> [https://github.com/search?q=author%3Azacharypatten+is%3Aissue+is%3Aopen](https://github.com/search?q=author%3Azacharypatten+is%3Aissue+is%3Aopen)
>
> Just modify the parameters to adjust your query as needed.

</p>
</details>
