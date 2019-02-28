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
