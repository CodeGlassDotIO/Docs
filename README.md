# CodeGlass Docs

These are the CodeGlass docs based on a [starter template](https://vsoch.github.com/docsy-jekyll/) for a Docsy jekyll theme, based on the Beautiful [Docsy](https://github.com/google/docsy) that renders with Hugo. This version is intended for
native deployment on GitHub pages. The original [Apache License](https://github.com/vsoch/docsy-jekyll/blob/master/LICENSE) is included.

CodeGlass specific instructions are prefixed with CG.

## Usage

### 1. CG Get the code

You can clone the repository right to where you want to host the docs:

```bash
git clone https://github.com/CodeGlassDotIO/Docs.git docs
cd docs
```

### 2. Customize

To edit configuration values, customize the [_config.yml](https://github.com/vsoch/docsy-jekyll/blob/master/_config.yml).
To add pages, write them into the [pages](https://github.com/vsoch/docsy-jekyll/blob/master/pages) folder. 
You define urls based on the `permalink` attribute in your pages,
and then add them to the navigation by adding to the content of [_data/toc.myl](https://github.com/vsoch/docsy-jekyll/blob/master/_data/toc.yml).
The top navigation is controlled by [_data/navigation.yml](https://github.com/vsoch/docsy-jekyll/blob/master/_data/navigation.yml)

### 3. Options

Most of the configuration values in the [_config.yml](https://github.com/vsoch/docsy-jekyll/blob/master/_config.yml) are self explanatory,
and for more details, see the [getting started page](https://vsoch.github.io/docsy-jekyll/docs/getting-started)
rendered on the site.

### 4. CG Serve


Instructions on installing Jekyll on windows (29-12-2021) (based on https://jekyllrb.com/docs/installation/windows/)

- Download and install Ruby+Devkit 3.3.7-1 from RubyInstaller Downloads (https://rubyinstaller.org/downloads/) 
- Use default options for installation.
- Run the ridk install step on the last stage of the installation wizard. This is needed for installing gems with native extensions. You can find additional information regarding this in the RubyInstaller Documentation
- Open a **new** command prompt window (or powershell, no admin mode needed) from the start menu. This ensures that changes to the PATH environment variable becomes effective. Install Jekyll and Bundler using: `gem install jekyll bundler`
- Check if Jekyll has been installed properly: `jekyll -v`

Then open a command promt (or powershell) in the repository folder (where this Readme.md file is located). (I usally go there through file explorer then SHIFT+right click on an empty spot and then "Open PowerShell window here")
- enter in the command prompt: `bundle install`



Depending on how you installed jekyll:



```bash 
# (Recommended)
bundle exec jekyll serve
# or
jekyll serve
```

**NOTE:** If the above serve command throws an error saying `require': cannot load such file -- webrick (LoadError)` try to run `bundle add webrick` to automatically add the webrick gem to your Gemfile, or manually add `gem "webrick"` line to the Gemfile and then run the serve command again.

**NOTE:** If the above serve command throws an error saying `cannot load such file -- rexml/parsers/baseparser (LoadError)` add the following gems to the gemfile, `gem "github-pages", "212", group: :jekyll_plugins` `gem "webrick"` `gem "jekyll", "3.9.0"` `gem "jekyll-feed", "0.15.1"`. Then run `bundle install` and then run the serve command again. 


### 5. Run as a container in dev or prod

#### Software Dependencies

If you want to run docsy jekyll via a container for development (dev) or production (prod) you can use containers. This approach requires installing [docker-ce](https://docs.docker.com/engine/install/ubuntu/) and [docker-compose](https://docs.docker.com/compose/install/). 

#### Customization

Note that the [docker-compose.yml](docker-compose.yml) file is using the [jekyll/jekyll:3.8](https://hub.docker.com/r/jekyll/jekyll/tags) image. If you want to make your build more reproducible, you can specify a particular version for jekyll (tag). Note that at the development time of writing this documentation, the latest was tag 4.0.0,
and it [had a bug](https://github.com/fastai/fastpages/issues/267#issuecomment-620612896) that prevented the server from deploying.

If you are deploying a container to production, you should remove the line to
mount the bundles directory to the host in the docker-compose.yml. Change:

```yaml
    volumes: 
      - "./:/srv/jekyll"
      - "./vendor/bundle:/usr/local/bundle"
      # remove "./vendor/bundle:/usr/local/bundle" volume when deploying in production
```

to:

```yaml
    volumes: 
      - "./:/srv/jekyll"
```

This additional volume is optimal for development so you can cache the bundle dependencies,
but should be removed for production. 

#### Start Container

Once your docker-compose to download the base container and bring up the server:

```bash
docker-compose up -d
```

You can then open your browser to [http://localhost:4000](http://localhost:4000)
to see the server running.

> Node : changes `baseurl: ""` in _config.yml  when you are running in local and prod according to the requirement.
