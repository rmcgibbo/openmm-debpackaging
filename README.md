openmm-debpackaging
===================

1. Get clean source distribution from the "ubstream" openmm repository.
Make a tarball of it named `openmm_<version>.orig.tar.gz`. Untar the
directory, and `cd` inside.

2. Clone this repo inside of it, and name the folder "debian".

```
git clone git@github.com:rmcgibbo/openmm-debpackaging.git debian
```

Now you should have a layout like

```
/openmm_5.2.orig.tar.gz
/openmm_5.2/
    /debian      <-- new
    CMakeLists.txt
    cmake_modules/
    docs/
    examples/
    [etc]
    
```

3. If you want to test the build, build the full binary package with `dpkg-buildpackage -rfakeroot`. But
for going to the next step you need to just the source only package:

```
dpkg-buildpackage -S
```



4. Push the debs to the ppa.

```
dput ppa:rmcgibbo/openmm ../openmm_5.2-0ubuntu1_amd64.changes
```
