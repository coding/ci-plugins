# email

通过email发送构建消息的插件

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: notify
      image: drillster/drone-email
      settings:
        host: smtp.some-server.com
        username: foo
        password: bar
        from: drone@your-domain.com
```

## 参数含义

from
: Send notifications from this address

host
: SMTP server host

port
: SMTP server port, defaults to `587`

username
: SMTP username

password
: SMTP password

skip_verify
: Skip verification of certificates, defaults to `false`

recipients
: List of recipients to send this mail to (besides the commit author)

recipients_file
: Filename to load additional recipients from (textfile with one email per line) (besides the commit author)

recipients_only
: Do not send mails to the commit author, but only to recipients, defaults to `false`

subject
: The subject line template ([handlebars](http://handlebarsjs.com/expressions.html) template)

body
: The email body template ([handlebars](http://handlebarsjs.com/expressions.html) template). This can be an inline template, or a URL (`file:///` allowed)

attachment
: An optional file to attach to the sent mail(s). This can be an absolute path or a path relative to the working directory

### Template Reference

repo.fullName
: repository full name

repo.owner
: repository owner

repo.name
: repository name

repo.SCM
: repository SCM (git)

repo.link
: link to the repository

repo.avatar
: repository avatar URL

repo.branch
: repository default branch

repo.private
: repository is private

repo.trusted
: repository is trusted

remote.URL
: remote clone URL

commit.SHA
: git commit SHA

commit.ref
: git commit ref (`/refs/heads/master`)

commit.branch
: git commit branch (`master`)

commit.link
: link to git commit

commit.message
: git commit message

commit.author.name
: git commit author name

commit.author.email
: git commit author email address

commit.author.avatar
: git commit author avatar URL

build.number
: build number

build.event
: build event, one of `push`, `pull_request`, `tag`, `deployment`

build.status
: build status, either `success` or `failure`

build.link
: link to the build details in Drone

build.created
: unix timestamp specifying when the build was created (in seconds)

build.started
: unix timestamp specifying when the build was started (in seconds)

build.finished
: unix timestamp specifying when the build was finished (in seconds)

prev.build.status
: previous build status, either `success` or `failure`

prev.build.number
: previous build number

prev.commit.SHA
: previous build git commit SHA

job.status
: matrix job status, either `success` or `failure`

job.exitCode
: matrix job exit code

job.started
: unix timestamp specifying when the matrix job was started (in seconds)

job.finished
: unix timestamp specifying when the matrix job was finished (in seconds)

yaml.signed
: Drone YAML is signed

yaml.verified
: Drone YAML is verified

tag
: created git tag

pullRequest
: pull request number

deployTo
: deployment environment

### Template Functions

uppercasefirst
: converts the first character of a string to uppercase

uppercase
: converts a string to uppercase

lowercase
: converts a string to lowercase. Example `{{lowercase commit.author.name}}`

datetime
: converts a unix timestamp to a date time string, using a format and a timezone. Example `{{datetime build.created "Mon Jan 2 15:04:05 MST 2006" "Local"}}`

success
: conditional which returns true if the build is successful

failure
: conditional which returns true if the build has failed

truncate
: returns a truncated string to n characters. Example `{{truncate commit.SHA 8}}`

urlencode
: returns a url encoded string

## 更多用法

更多用法参考：[drillster/drone-email](https://github.com/drillster/drone-email)
