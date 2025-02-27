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

It's highly suggest to use any Linux distro _(Ubuntu: highly recommended)_ compared to Windows. Most of the cases, you won't face any issues while building the project within your local system if you follow the instruction below properly. But if you're facing any issue, you can post them within the repo discussion [Help Request](https://github.com/Grow-with-Open-Source/Notebook/discussions/3 "Goto Help Request Discussion")...

#### For Ubuntu:

If you're using a Linux distribution - **Ubuntu**, follow these steps:

- Install `Ruby` and other prerequisites:
```bash
sudo apt-get install ruby-full build-essential zlib1g-dev -y
```

> Avoid installing RubyGems packages (called gems) as the root user. Instead, set up a gem installation directory for your user account. The following commands will add environment variables to your `~/.bashrc`{: .file-path} file to configure the gem installation path:
```bash
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```
{: .prompt-info}

- Use the following command, to check whether `Ruby` has properly installed and its PATH has been set properly.
```bash
ruby -v
```

- Finally, install Jekyll and Bundler:
```bash
gem install jekyll bundler
```

> For Other Linux Distros, check the offical Jekyll webpage[^other-linux-distros-installation]. Also make sure, you have installed `bundler` along with jekyll using the follow command:
```bash
gem install bundler
```
{: .prompt-tip}

- Use the following command to check whether the `bundler` and jekyll framework installed properly or not.
```bash
bundle info --path jekyll-theme-chirpy
```

#### For Windows:

For Windows users, setting up the environment is a bit more involved:

- Start by downloading and installing the the `Ruby` using [RubyInstaller](https://rubyinstaller.org/downloads/ "Download RubyInstaller"), choose the the latest one with Devkit with default options.

- At the end of installation, You'll get CMD asking you to enter option between 1-3. Enter 3 as input, then you can enter 2 if you want to update `MYSYS2` but that's totally optional. After all the installation is done, press enter to close the CMD prompt.
![prompt-img](cmd-prompt-img.png)

- Use the following command, to check whether `Ruby` has properly installed and its PATH has been set properly.
```powershell
ruby -v
```

- Open a new command prompt window from the start menu and install Jekyll and Bundler:
```powershell
gem install jekyll bundler
```

- Use the following command to check whether the `bundler` and jekyll framework installed properly or not.
```bash
bundle info --path jekyll-theme-chirpy
```

#### For MacOS:

If you're on MacOS, follow these steps:

> Ensure you have the [Homebrew](https://brew.sh/ "Install Homebrew") package manager installed. If you're facing any issues while setting up the project in MacOS, check out the [Trobleshooting post](https://github.com/Grow-with-Open-Source/Notebook/discussions/3#discussioncomment-7151280) within the [Help Request](https://github.com/Grow-with-Open-Source/Notebook/discussions/3 "Goto Help Request Discussion") discussion.
{: .prompt-warning}

- Install `chruby` and `ruby-install` with Homebrew:
```bash
brew install chruby ruby-install xz
```

- Install the latest stable version of Ruby _(supported by Jekyll[^jekyll-offical-website])_:
```bash
ruby-install ruby 3.1.3
```

- This will take a few minutes, and once it’s done, configure your shell to automatically use chruby:
```bash
echo "source $(brew --prefix)/opt/chruby/share/chruby/chruby.sh" >> ~/.zshrc
echo "source $(brew --prefix)/opt/chruby/share/chruby/auto.sh" >> ~/.zshrc
echo "chruby ruby-3.1.3" >> ~/.zshrc # run 'chruby' to see actual version
```

> If you’re using Bash, replace `.zshrc` with `.bash_profile`. If you’re not sure, read this external guide to [find out which shell you’re using](https://www.moncefbelyamani.com/which-shell-am-i-using-how-can-i-switch/ "find you shell").
{: .prompt-info}

- Quit and relaunch Terminal, then check that everything is working:
```bash
ruby -v
```

- After installing Ruby with chruby, install the latest Jekyll & bundler gem:
```bash
gem install bundler jekyll
```

- Use the following command to check whether the `bundler` and jekyll framework installed properly or not.
```bash
bundle info --path jekyll-theme-chirpy
```

### **Building the Project**

After setting up the environment, you can start contributing to the project:

- Start by [forking](https://github.com/Grow-with-Open-Source/Notebook/fork "let's fork the repo") the repository.

- Clone the forked repository to your local machine.
  ```bash
  #cloning the repo
  git clone https://github.com/<your-github-user-name>/Notebook.git

  #entering the project directory
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
  twitter: Shamith29188225
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
  img_path: "/assets/img/<your_img_directory_name>/"
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
img_path: "/assets/img/welcome-page/"
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
