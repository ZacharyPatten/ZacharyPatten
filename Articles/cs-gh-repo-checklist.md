# C# GitHub Repository Checklist

Do you have a C# repository on GitHub? Are you thinking about making a C# repository on GitHub? This is a checklist intended to help you make the most out
of your GitHub repository.

<details>
<summary>
  :page_facing_up: Are you happy with the current URL (repo account and name)? <sub>[Expand]</sub>
</summary>
<p>

> Make sure you are happy with the name of your repo and the account your repo is under. You can rename and transer ownership of repositories, but that will change the URL of your repo, which may cause confusion for your community.
>
> GitHub has organization accounts, so if you already have a group of dedicated developers or intend to grow a community around the repository, having the repository be under an organization's account may be more appropriate than a personal account.<br/>
> [See more information on GitHub organization here.](https://docs.github.com/en/organizations/collaborating-with-groups-in-organizations/about-organizations)

</p>
</details>

<details>
<summary>
  :page_facing_up: Do you have a <code>LICENSE</code>? <sub>[Expand]</sub>
</summary>
<p>

> Licensing is very important. You should choose a license before you make any code public.
> [See GitHub's guide on licensing here.](https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/creating-a-repository-on-github/licensing-a-repository)

</p>
</details>

<details>
<summary>
  :page_facing_up: Do you have a <code>.gitignore</code>? <sub>[Expand]</sub>
</summary>
<p>

> You don't want all your files to be included in your repository. For example, you generally want all your source code files (`.cs` for C# files) to be included, but you do not want your `obj` and `bin` folders included. Repsoitories are generally for source code while packages and releases are for binaries. The `.gitignore` file is how you can control what files are included or excluded from your repository. For C# repsoitories, if you use GitHub's online interface, you want to choose the `Visual Studio` option when you create your repository:
>
> ![image](https://user-images.githubusercontent.com/3385986/126922682-eee60260-8cb8-473e-8808-bce382db40c3.png)
>
> If you need to add or update a `.gitignore` file to an existing repsoitory, you copy the latest version of the file form here:
> [https://github.com/github/gitignore/blob/master/VisualStudio.gitignore](https://github.com/github/gitignore/blob/master/VisualStudio.gitignore)
>
> [See git's documentation on `.gitignore` here.](https://git-scm.com/docs/gitignore)
  
</p>
</details>

<details>
<summary>
  :page_facing_up: Do you have a <code>.gitattributes</code>? <sub>[Expand]</sub>
</summary>
<p>

A `.gitattributes` file helps you control some settings. The most common use for this is to standardize line endings, so that when the code is cloned it will have the appropriate line endings based on the environment, but line endings will be standardized in the actual repository. For C# repositories, you generally just want to use this as your `.gitattributes`:
```
* text=auto
```
However, if you do have any binary files you should add explicit entries for those types of files. For example, if you have a `.png` image file in your repository you could add this line to your 

</p>
</details>

<details>
<summary>
  :page_facing_up: Do you have a <code>README.md</code>? <sub>[Expand]</sub>
</summary>
<p>

_todo_

</p>
</details>

<details>
<summary>
  :page_facing_up: Do you have a GitHub Actions Continuous Integration (CI) workflow? <sub>[Expand]</sub>
</summary>
<p>

_todo_

</p>
</details>

<details>
<summary>
  :page_facing_up: Do you have your target framework documented? <sub>[Expand]</sub>
</summary>
<p>

_todo_

</p>
</details>

<details>
<summary>
  :page_facing_up: Do you have recommended IDEs and build processes documented? <sub>[Expand]</sub>
</summary>
<p>

_todo_

</p>
</details>

<details>
<summary>
  :page_facing_up: Are <code>Issues</code> enabled on your repository? <sub>[Expand]</sub>
</summary>
<p>

_todo_

</p>
</details>

<details>
<summary>
  :page_facing_up: Do you have clearly defined labels for issues? <sub>[Expand]</sub>
</summary>
<p>

_todo_

</p>
</details>

<details>
<summary>
  :page_facing_up: Do you have clearly defined milestones for issues? <sub>[Expand]</sub>
</summary>
<p>

_todo_

</p>
</details>

<details>
<summary>
  :page_facing_up: Do you have a <code>.github/ISSUE_TEMPLATE/config.yml</code>? <sub>[Expand]</sub>
</summary>
<p>

_todo_

</p>
</details>

<details>
<summary>
  :page_facing_up: Do you have issue templates? <sub>[Expand]</sub>
</summary>
<p>

_todo_

</p>
</details>

<details>
<summary>
  :page_facing_up: Do you have a <code>.github/pull_request_template.md</code>? <sub>[Expand]</sub>
</summary>
<p>

_todo_

</p>
</details>

<details>
<summary>
  :page_facing_up: Are <code>Discussions</code> enabled on your repository? <sub>[Expand]</sub>
</summary>
<p>

_todo_

</p>
</details>

<details>
<summary>
  :page_facing_up: Do you have a logo? <sub>[Expand]</sub>
</summary>
<p>

_todo_

</p>
</details>

<details>
<summary>
  :page_facing_up: Do you have a <em>"using my project"</em> badge? <sub>[Expand]</sub>
</summary>
<p>

_todo_

</p>
</details>

<details>
<summary>
  :page_facing_up: Are you using GitHub Pages? <sub>[Expand]</sub>
</summary>
<p>

_todo_

</p>
</details>

<details>
<summary>
  :page_facing_up: Do You have documentation generation? <sub>[Expand]</sub>
</summary>
<p>

_todo_

</p>
</details>

<details>
<summary>
  :page_facing_up: Do you have a unit tests? <sub>[Expand]</sub>
</summary>
<p>

_todo_

</p>
</details>

<details>
<summary>
  :page_facing_up: Do you have unit testing code coverage? <sub>[Expand]</sub>
</summary>
<p>

_todo_

</p>
</details>

<details>
<summary>
  :page_facing_up: Do you have nuget packages? <sub>[Expand]</sub>
</summary>
<p>

_todo_

</p>
</details>

<details>
<summary>
  :page_facing_up: Do you have a <code>.editorconfig</code>? <sub>[Expand]</sub>
</summary>
<p>

_todo_

</p>
</details>

<details>
<summary>
  :page_facing_up: Do you have pull request templates? <sub>[Expand]</sub>
</summary>
<p>

_todo_

</p>
</details>

<details>
<summary>
  :page_facing_up: Do you have a change log? <sub>[Expand]</sub>
</summary>
<p>

_todo_

</p>
</details>

<details>
<summary>
  :page_facing_up: Do you have GitHub Sponsors set up? <sub>[Expand]</sub>
</summary>
<p>

_todo_

</p>
</details>

<details>
<summary>
  :page_facing_up: Do you markdown linting? <sub>[Expand]</sub>
</summary>
<p>

_todo_

</p>
</details>

<details>
<summary>
  :page_facing_up: Do you have branch policies configured? <sub>[Expand]</sub>
</summary>
<p>

_todo_

</p>
</details>

<details>
<summary>
  :page_facing_up: Do you have a chat location (discussions, discord, gitter, etc.)? <sub>[Expand]</sub>
</summary>
<p>

_todo_

</p>
</details>
