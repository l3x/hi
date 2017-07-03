After running the previous Hey example to install the Hey package on an Ubuntu box

We now want to install another go package using vendoring

    ~$ cd  ~/go
    ~/go$ mkdir hi-project
    ~/go$ export GOROOT=/usr/local/go
    ~/go$ export GOPATH=$HOME/go
    ~/go$ export GOPATH_ORIG=$GOPATH
    ~/go$ export GOBIN=$GOPATH/bin
    ~/go$ export PATH=$PATH:$GOROOT/bin:$GOBIN
    ~/go$ cd hi-project/
    ~/go/hi-project$ export GOPATH=$GOPATH_ORIG:$HOME/go/$PROJECT
    ~/go/hi-project$ mkdir vendor
    ~/go/hi-project$ cd vendor/
    ~/go/hi-project/vendor$ go get github.com/l3x/hi/...
    ~/go/hi-project/vendor$ cd ..
    ~/go/hi-project$ nano main.go
    ~/go/hi-project$ go install
    ~/go/hi-project$ hi-project
    Hi
    ~/go/hi-project$ which hi-project
    /home/lex/go/bin/hi-project
    ~/go/hi-project$ tree ~/go
    /home/lex/go
    ├── bin
    │   ├── hey-project
    │   └── hi-project
    ├── hey-project
    │   └── main.go
    ├── hi-project
    │   ├── main.go
    │   └── vendor
    ├── pkg
    │   └── linux_amd64
    │       └── github.com
    │           └── l3x
    │               ├── hey.a
    │               └── hi.a
    └── src
        └── github.com
            └── l3x
                ├── hey
                │   ├── hey.go
                │   └── README.md
                └── hi
                    ├── hi.go
                    └── README.md
    
    13 directories, 10 files
    