---
title: Contribute to Notebook
date: 2023-09-27 13:23:00 +0530
categories: [Welcome, Tutorial]
tags: [introduction, markdown]
media_subpath: "/assets/img/contribute-to-notebook"
image:
  path: "page-cover.png"
  alt: "Contribution Page"
author: shamith_watchdogs
pin: true
---

Welcome to the [**Notebook**](https://github.com/Grow-with-Open-Source/Notebook "Goto original Repo") open-source project, where you can be a part of a thriving community of technical writers and developers! This project utilizes GitHub's Jekyll[^jekyll-offical-website] framework to create a dynamic platform for sharing technical knowledge and learning from one another. Whether you're a beginner eager to learn or an experienced developer looking to contribute, Notebook offers a win-win opportunity for all.

## Getting Started

### Setting up Environment

Let's start by setting up the project within your local system. Most of the cases, you won't face any issues while building the project within your local system if you follow the instruction below properly. But if you're facing any issue, you can post them within the repo discussion [Help Request](https://github.com/Grow-with-Open-Source/Notebook/discussions/3 "Goto Help Request Discussion")...

#### Using Dev Container

This approach is platform independent as it uses Docker to create the isolated development environment within dev container. You can use it Windows, Linux and MacOS system with ease. Let's start from scratch, shall we ???...

- Start by downloading and Installing [Docker Desktop](https://www.docker.com/products/docker-desktop/ "go download docker desktop") on your system.
- Then download and install [VS Code](https://code.visualstudio.com/ "go download vs code").
- Within your VS Code, Install [Dev Container extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers "go install dev-container extension") from the extensions tab.

Well that's it... You got the all the things are ready and all you gotta do is reopen the project file by clicking <kbd>Reopen in container</kbd>, just as shown below...

![Dev Container Demo](../dev-container-demo.gif)

Dev container does all the heavy lifting for you and creates a container and setup the required environment for you. Now, you can write your blog within this dev container and then commit and push your changes though the shell of the container.

> If you're doing this for the first time, it might take a while depending on your system specs. 
 {: .prompt-tip }

#### For Windows:

Coming to windows-based system, it highly recommended to use [Dev Container](#using-dev-container) approach as it simplifies the complex installation and dependencies handling. But if you wish to go for a native installation, You can find it in the below disclosed details below.

<details>
<summary>Native Installation <b>(Not Recommended)</b></summary>

<p>So you want to do things in a hard way. It's not like we're hear to judge you, but all we got to say is that "<b>THIS 👇</b>" is one heck of a process you have to go through. Can't you just stick to <a href="#using-dev-container" title="go back to dev container">Dev Container</a> ???...</p>

<p>Anyways, Here's how you can setup the required environment thought native installation in Windows...</p>

<ul>
  <li>Start by downloading and installing the <code class="language-plaintext highlighter-rouge">Ruby</code> using <a href="https://rubyinstaller.org/downloads/" title="Download RubyInstaller" target="_blank">Ruby Installer</a>, and choose the latest one with Devkit with default options.</li>
  <li>Run <code class="language-plaintext highlighter-rouge">ridk install</code> on command prompt, If the installer doesn't prompt you the following image at the end of the installation...</li>
  <a href="/Notebook/assets/img/contribute-to-notebook/cmd-prompt-img.png" class="popup img-link"><img src="/cmd-prompt-img.png" alt="prompt-img" loading="lazy"></a>
  <li>Go ahead and select <kbd>MSYS2 and MINGW development toolchain</kbd> option by pressing <code class="language-plaintext highlighter-rouge">3</code> + <kbd>Enter</kbd></li>
  <li>Open a new command prompt window from the start menu, Use the following command to check whether <code class="language-plaintext highlighter-rouge">Ruby</code> has been properly installed and its <code class="language-plaintext highlighter-rouge">PATH</code> has been set properly.</li>
  <div class="language-powershell highlighter-rouge"><div class="code-header">
  <span data-label-text="Powershell"><i class="fas fa-code fa-fw small"></i></span>
  <button aria-label="copy" data-title-succeed="Copied!"><i class="far fa-clipboard"></i></button></div>
  <div class="highlight">
  <code><table class="rouge-table"><tbody><tr><td class="rouge-gutter gl"><pre class="lineno">1
</pre></td><td class="rouge-code"><pre><span class="n">ruby</span><span class="w"> </span><span class="nt">-v</span><span class="w">
</span></pre></td></tr></tbody></table></code></div></div>
  <li>Now use the following command to install <code class="language-plaintext highlighter-rouge">Jekyll</code> and <code class="language-plaintext highlighter-rouge">Bundler</code>:</li>
  <div class="language-powershell highlighter-rouge">
  <div class="code-header">
  <span data-label-text="Powershell"><i class="fas fa-code fa-fw small"></i></span>
  <button aria-label="copy" data-title-succeed="Copied!"><i class="far fa-clipboard"></i></button></div>
  <div class="highlight">
  <code><table class="rouge-table"><tbody><tr><td class="rouge-gutter gl"><pre class="lineno">1
</pre></td><td class="rouge-code"><pre><span class="n">gem</span><span class="w"> </span><span class="nx">install</span><span class="w"> </span><span class="nx">jekyll</span><span class="w"> </span><span class="nx">bundler</span><span class="w"> </span><span class="nx">jekyll-theme-chirpy</span><span class="w">
</span></pre></td></tr></tbody></table></code></div>
</div>
  <li>Now, your system is ready to build and use the project locally.</li>
</ul>
<blockquote class="prompt-tip">
  <p>You can checkout <a href="https://jekyllrb.com/docs/installation/" title="goto jekyll docs" target="_blank">Jekyll Docs</a> for more details regarding installation.</p>
</blockquote>
</details>

#### For Unix-based Systems:

For Unix-based systems, it's **recommended** to go for **native installation** but you can do for [Dev Container](#using-dev-container "go back to dev-containers") if you want some application-level isolation. Now that's out of our way, let's take a took at the installation process...

- Installing Jekyll framework with required dependcies based on your system/distro from [Jekyll official docs](https://jekyllrb.com/docs/installation/ "goto jekyll docs").
- And that's it... you're done, you got required environment for running project.

Just so that we get a glimpse of a native installation, let's take a look how we do things in unix-based system by taking **Ubuntu** _(most popular distro used from beginners to general-purpose user and power users)_.

- Starting up by updating your system file using,
```bash
sudo apt update -y && sudo apt upgrade -y
```

- Now it's time for `ruby` and other core dependencies,
```bash
sudo apt -y install ruby-full build-essential zlib1g-dev
```

- Now that we've got our core dependencies, let's add environment variables,
```bash
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
```

> Note that as it's not recommended to install or set environmental variable on `root` level and keep things `user` level, atleast as recommended by [official docs](https://jekyllrb.com/docs/installation/ "goto jekyll docs"). But if you still want to do, just make sure you know what you're doing.
{: .prompt-info}

- Now, let's source the `~/.bashrc`{: .file-path} to access the environmental variable within the current session.
```bash
source ~/.bashrc
```

- Now that we have installed dependecies and configured all the environmental varible, let's test if `ruby` is installed properly or not...
```bash
ruby -v
```

- Finish up the installation by installing required dependecies for the project,
```bash
gem install jekyll bundler jekyll-theme-chirpy
```

- And it's done, now you have the required environment to run the project.

#### For MacOS:

Coming to MacOs-based system, it kinda similar situtation with [Unix-based system](#for-unix-based-systems "goto unix-based system section") 'cause it's one of the offspring of Unix-based system. Anyways, all I was trying to say is that you can either with **native installation** _(which is recommended)_ or [Dev Container](#using-dev-container "go back to dev-containers") _(another fairly good option)_. And if you want to proceed with native installation, here's how you can do it...

- Make sure you have [Homebrew](https://brew.sh/ "Install Homebrew") package manager installed. If not you can install using,
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

> If you're facing any issues while setting up the project in MacOS, check out the [Trobleshooting post](https://github.com/Grow-with-Open-Source/Notebook/discussions/3#discussioncomment-7151280) within the [Help Request](https://github.com/Grow-with-Open-Source/Notebook/discussions/3 "Goto Help Request Discussion") discussion.
{: .prompt-info}

- Now we're going install `chruby` as version manager to install and manager various version of `ruby`
```zsh
brew install chruby ruby-install
```

- Let's go ahead and install `ruby` version 3.4.1 which is recommended by [official docs](https://jekyllrb.com/docs/installation/macos/ "open jekyll docs").
```zsh
ruby-install ruby 3.4.1
```

- Now that's done, let's configure the shell for `chruby` to work as expected.
```zsh
echo "source $(brew --prefix)/opt/chruby/share/chruby/chruby.sh" >> ~/.zshrc
echo "source $(brew --prefix)/opt/chruby/share/chruby/auto.sh" >> ~/.zshrc
echo "chruby ruby-3.4.1" >> ~/.zshrc # run 'chruby' to see actual version
```

> If you’re using Bash, replace `.zshrc` with `.bashrc` or `.bash_profile` . If you’re not sure, read this external guide to [find out which shell you’re using](https://www.moncefbelyamani.com/which-shell-am-i-using-how-can-i-switch/ "find you shell").
{: .prompt-info}

- Now that we have configured `chruby`, let's make sure the changes are updated within our current session,
```zsh
source ~/.zshrc
#
# If your default shell is bash, then use the following
#
# source ~/.bashrc
#
#      (or)
#
# source ~/.bash_profile
#
# depending on where you have configured
```

- Time for testing !!!... Let's see if `ruby` is installed properly or not,
```zsh
ruby -v
```

- Finally, let's install the core dependencies for the project...
```zsh
gem install jekyll bundler jekyll-theme-chirpy
```

- Now you're ready to use the project...

### **Building the Project**

After setting up the environment, you can start contributing to the project:

- Start by [forking](https://github.com/Grow-with-Open-Source/Notebook/fork "let's fork the repo") the repository.

- Clone the forked repository to your local machine.
  ```bash
  # cloning the repo
  git clone https://github.com/<your-github-user-name>/Notebook.git

  # entering the project directory
  cd Notebook
  ```

- Use the following command to install project dependencies.
```bash
bundle
```

- Host the static website locally using the following command to preview the current state of the project.
```bash
bundle exec jekyll s
```

> Use `--incremental` argument to update the project live while working on it...
```bash
bundler exec jekyll s --incremental
```
{: .prompt-tip}

> If project build is successful, then you can view the project build that is hosted through your [localhost:4000/Notebook](http://127.0.0.1:4000/Notebook/). Well done, you have successfully setted up the project within your local system.
{: .prompt-info}

## Contribution Guidelines

To contribute effectively, please follow these guidelines:

- All of the technical writing will be done in Markdown format. So, Make yourself more comfortable Markdown sytnax through [Offical GitHub Documentation](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/quickstart-for-writing-on-github "visit the offical GitHub Docs").

- Since this open source is based chripy[^chripy-offical-website] theme jekyll project, You're not limited by Markdown only. You can do much more using simple Markdown that support limited HTML elements. Check out the Chirpy-based [post creation](https://chirpy.cotes.page/posts/write-a-new-post/) and [text and typography](https://chirpy.cotes.page/posts/text-and-typography/).

- Place your technical writing files within the **`_posts`{: .filepath}.** directory, following the naming convention **`YYYY-MM-DD-file-name.md`**, e.g., `2023-09-27-welcome-to-notebook.md`. **Use lowercase letters and separate words with a single dash.**

- Add your author details to the **`_data/authors.yml`{: .filepath}.** file in the following format:
```yaml
unique_key_value:
    name: <author_name>
    twitter: <twitter_id>
    url: <personal (or) contact url>
```

> For example:
```yaml
shamith_watchdogs:
  name: Shamith Nakka
  twitter: shamith_nakka
  url: https://github.com/iamwatchdogs/
```
{: .prompt-tip file='_data/authors.yml'}

- Store images used in your content in **`assets/img/<your-project-name>/`{: .filepath}**. While using external CDN links is recommended, you can also place files in this directory if necessary.

- Each technical writing Markdown file should begin with the following configuration:
  ```md
  ---
  title: <title>
  date: YYYY-MM-DD HH:MM:SS +/-TTTT
  categories: [<main_categories>, <sub_categories_1>, ..., <sub_categories_n>]
  tags: [<tag_1>, ..., <tag_n>]
  author: <respective_author_key_value>
  media_subpath: "/assets/img/<your_img_directory_name>/"
  image:
    path: <name_of_the_img_for_page_cover>
    alt: <alternative_text>
  ---

  # Your content writing begins here
  ```

> Example:
```md
---
title: Welcome to the Notebook
date: 2023-09-21 20:34:00 +0530
categories: [Welcome, Guide]
tags: [introduction]
author: shamith_watchdogs
media_subpath: "/assets/img/welcome-page/"
image:
  path: "welcome-img.jpg"
  alt: "Welcome Page"
---
```
{: .prompt-tip file='_posts/2023-09-21-welcome-page.md'}

> Note that the `+/-TTTT` in the `date` section refers the **UTC offset**. You can find your **UTC offset** value by searching for your country in the [list of UTC](https://en.wikipedia.org/wiki/List_of_UTC_offsets "Goto List of UTC offsets"). And if you're from India, you can use the above UTC offset from the example.
{: .prompt-info}

Please ensure your contributions adhere to these guidelines to maintain consistency and make the project more accessible and user-friendly. **Happy contributing!**

## Footnote

[^jekyll-offical-website]: **GitHub's Jekyll Framework offical Page:** <https://jekyllrb.com>
[^other-linux-distros-installation]: **Other Linux Distro Installation:** <https://jekyllrb.com/docs/installation/other-linux/>
[^chripy-offical-website]: **Chirpy Jekyll theme's Offical Website:** <https://github.com/cotes2020/jekyll-theme-chirpy>
