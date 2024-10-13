[practice guide](https://www2.mmm.ucar.edu/projects/mpas-jedi/tutorial/202410HOWARD)

### Export environmental variables `staged_data` and `tutorial`
```
[[ -d /scratch1 ]] && export staged_data=/scratch1/BMC/wrfruc/gge/jedi_tests #for Hera
[[ -d /lfs5 ]] && export staged_data=/lfs5/BMC/wrfruc/gge/jedi_tests #for Jet

export tutorial=/scratch1/BMC/wrfruc/gge/jedi_tests/tutorial  # Users's own directory
```

### Prepare
```
cd ${tutorial}/..
cp -rp ${staged_data}/mpasjedi_tutorial202410HOWARD $tutorial
cd $tutorial
mkdir mpas_bundle_v3
cd mpas_bundle_v3
git clone --recursive https://github.com/NOAA-EMC/RDASApp code
cd code
./build.sh -j10
cd ..
ln -snf code/build build
```


