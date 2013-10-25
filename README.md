openmm-debpackaging
===================

1. Get clean source distribution from the "ubstream" openmm repository.
Make a tarball of it openmm_<version>.orig.tar.gz. Untar the directory,
and cd inside.

2. Clone this repo inside of it, and name the folder "debian".

```
git clone git@github.com:rmcgibbo/openmm-debpackaging.git debian
```

Now you should have

/openmm_5.2.orig.tar.gz
/openmm_5.2/
    /debian      <-- new
    CMakeLists.txt
    cmake_modules/
    docs/
    examples/
    [etc]
    


3. Build the debian packages. This command seemed to work for me.

```
dpkg-buildpackage -rfakeroot
```

4. Push the debs to the ppa.

```
dput ppa:rmcgibbo/openmm ../openmm_5.2-0ubuntu1_amd64.changes
```
