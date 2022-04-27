# EmbeddedLciMpc.jl
This is a simple example that embed julia into C++

## Usage 
First we have to instantiate the julia environment. Open the Julia REPL in the project directory, then run:

```
using Pkg
Pkg.activate(".")
Pkg.instantiate()
exit()
```

To create the cpp exectuable, runs the following
```
mkdir build 
cd build 
cmake ..
make
```
You can see the current example with 
```
./main
```

## Issues and TODOs
1. ContactImplicitMPC uses meshcat, which can't be built in the docker environment without some dependencies
    * TODO: add this to Dockerfile `apt get install -y unzip`
2. Need to install Julia on docker environment
    * TODO: add the following
    ```
    curl https://julialang-s3.julialang.org/bin/linux/x64/1.6/julia-1.6.6-linux-x86_64.tar.gz -o julia-1.6.6-linux-x86_64.tar.gz

    tar -xvzf julia-1.6.6-linux-x86_64.tar.gz

    sudo mv julia-1.6.6/ /opt/

    sudo ln -s /opt/julia-1.6.6/bin/julia /usr/local/bin/julia
    ```
