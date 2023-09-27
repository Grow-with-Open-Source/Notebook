---
title: Contribute to Notebook
date: 2023-09-27 13:23:00 +0530
categories: [Welcome, Tutorial]
tags: [introduction, markdown]
img_path: "../../assets/img/contribute-to-notebook"
author: shamith_watchdogs
pin: true
---

Welcome to the **Notebook** open-source project, where you can be a part of a thriving community of technical writers and developers! This project utilizes GitHub's Jekyll framework to create a dynamic platform for sharing technical knowledge and learning from one another. Whether you're a beginner eager to learn or an experienced developer looking to contribute, Notebook offers a win-win opportunity for all.

## Getting Started

### System Requirements

It's highly recommended to use any Linux distro compared to Windows. Most of the cases, you won't face any issues while building the project within your local system if you follow the instruction below properly. But if you're facing any issue, you can post them within the repo discussion [Troubleshooting](https://github.com/Grow-with-Open-Source/Notebook/discussions/2 "Goto Troubleshooting Discussion")...

#### For Linux Distros:

If you're using a Linux distribution, follow these steps:

> Update and upgrade your system:

```bash
sudo apt update -y && sudo apt full-upgrade -y
```

> Install Ruby and essential dependencies:

```bash
sudo apt-get install ruby-full build-essential zlib1g-dev
```

> If you encounter any issues, try these commands:

```bash
sudo snap install ruby --classic
gem install jekyll bundler
```

#### For Windows:

For Windows users, setting up the environment is a bit more involved:

- Start by downloading and installing the the Ruby using [RubyInstaller](https://rubyinstaller.org/downloads/ "Download RubyInstaller"), choose the the latest one with Devkit with default options.
- At the end of installation, You'll get CMD asking you to enter option between 1-3. Enter 1 and then 3 as input one after another. After all the installation is done, press enter to close the CMD prompt.
  ![prompt-img](cmd-prompt-img.png)
- Open a new command prompt window from the start menu and install Jekyll and Bundler:

```bash
gem install jekyll bundler
```

#### For MacOS:

If you're on MacOS, follow these steps:

Ensure you have the [Homebrew](https://brew.sh/ "Install Homebrew") package manager installed.

Use the following commands to install Ruby and Bundler:

```bash
brew install ruby
gem install jekyll bundler
```

### Building the Project

After setting up the environment, you can start contributing to the project:

- Start by forking the repository.

- Clone the forked repository to your local machine.

- Use the following command to install project dependencies.

```bash
bundle
```

- Host the static website locally using the following command to preview the current state of the project.

```bash
bundle exec jekyll s
```

## Contribution Guidelines

To contribute effectively, please follow these guidelines:

- All of the technical writing will be done in Markdown format. So, Make yourself more comfortable Markdown sytnax through [Offical GitHub Documentation](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/quickstart-for-writing-on-github "visit the offical GitHub Docs").

- Since this open source is based [chripy](https://github.com/cotes2020/jekyll-theme-chirpy "visit offical chirpy theme repo") theme jekyll project, You're not limited by Markdown only. You can do much more using simple Markdown that support limited HTML elements. Check out the chirpy theme based writing[^chirpy-theme-writing].

- Place your technical writing files within the **`\_posts`** directory, following the naming convention **`YYYY-MM-DD-file-name.md`**, e.g., `2023-09-27-welcome-to-notebook.md`. **Use lowercase letters and separate words with a single dash.**

- Add your author details to the **`\_data/authors.yml`** file in the following format:

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

- Store images used in your content in **`assets/img/<your-project-name>/`**. While using external CDN links is recommended, you can also place files in this directory if necessary.

- Each technical writing Markdown file should begin with the following configuration:

```md
---
title: <title>
date: YYYY-MM-DD HH:MM:SS +/-TTTT
categories: [<main_categories>, <sub_categories_1>, ..., <sub_categories_n>]
tags: [<tag_1>, ..., <tag_n>]
author: <respective_author_key_value>
img_path: "../../assets/img/<your_img_directory_name>/"
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
img_path: "../../assets/img/welcome/"
image:
  path: "welcome-img.jpg"
  alt: "Welcome Page"
---
```

Please ensure your contributions adhere to these guidelines to maintain consistency and make the project more accessible and user-friendly. Happy contributing!

## Footnote

[^chirpy-theme-writing]: Chirpy-based [post creation](https://chirpy.cotes.page/posts/write-a-new-post/) and [text and typography](https://chirpy.cotes.page/posts/text-and-typography/).
