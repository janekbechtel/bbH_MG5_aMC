# bbH_MG5_aMC

wget https://launchpad.net/mg5amcnlo/2.0/2.6.x/+download/MG5_aMC_v2.6.5.tar.gz

tar -xvf MG5_aMC_v2.6.5.tar.gz

cd MG5_aMC_v2_6_5/

wget https://cp3.irmp.ucl.ac.be/projects/madgraph/raw-attachment/wiki/bbH/bbH_4FS_ybyt_v2.6.1.tar.gz

wget https://cp3.irmp.ucl.ac.be/projects/madgraph/raw-attachment/wiki/bbH/bbH_4FS_yb2_v2.6.1.tar.gz

tar -xvf bbH_4FS_ybyt_v2.6.1.tar.gz

tar -xvf bbH_4FS_yb2_v2.6.1.tar.gz

export VO_CMS_SW_DIR=/cvmfs/cms.cern.ch

source $VO_CMS_SW_DIR/cmsset_default.sh

scram project CMSSW_8_0_22

cd CMSSW_8_0_22/src

cmsenv

cd -

./bin/mg5

generate p p > h b b~ [QCD]

output bbH_test


exit

# Further instructions
     Delete bbH_test folder, copy bbH folders under main MG5 directory and go to bbH4FS_yb2 or bbH4FS_ybyt folder.

     The following applies to both
     folders bbH4FS_yb2 and bbH4FS_ybyt, go inside one of the two and:

     First:

       a) adjust mg5_path path in Cards/amcatnlo_configuration.txt

       b) if want to use lhapdf (to access PDF4LHC_nlo_nf4 (92000)) add in amcatnlo_configuration.txt
       lhapdf = /afs/cern.ch/cms/slc6_amd64_gcc530/external/lhapdf/6.1.6-ikhhed/bin/lhapdf-config     
       (see location of lhapdf with scram tool info lhapdf; setenv SCRAM_ARCH slc6_amd64_gcc530 - setup compiler used for 6.1.6. CMSSW_8_0_3) 

       c) comment fastjet setting

     Run the process with 

        ./bin/generate_events

     Results (and event files) will be found in: Events/run_*

    Inputs can be set in:
       Cards/param_card.dat
       Cards/run_card.dat
      (Cards/shower_card.dat -- for shower inputs in case you run the shower via MG5_aMC)
