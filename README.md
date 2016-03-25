# nginxify

Nginx is one of the most widely used webserver or load balancers. But usually how long does it take for you to get one up and running if you just want a quick server to host static files for you. 

I use Ansible to install Nginx so you are going to need Homebrew and ansible which you can install by doing this. 

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

It's likely that you have homebrew already if you're a Mac user. Next you're going to need Ansbible

```
brew install ansible
```

## One small manual process

You need to include this line in `/usr/local/etc/nginx/nginx.con` after `include server/*;`

```
include /usr/local/etc/nginx/sites-enabled/*;
```

Then you can just run `go` command

```
./go
```

This command will run ansible playbook which will install Nginx from homebrew and configure to the minimum with `http://web.local` as your domain. 

The html folder will be in your home directory `${HOME}/www`

Now go to your browser `http://web.local`
