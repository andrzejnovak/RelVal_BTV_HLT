# RelVal_BTV_HLT
Release Validation for BTV (b-tagging) at HLT (High Level Trigger)

## Find datasets
https://cmsweb.cern.ch/das/request?input=dataset%20status=*%20dataset=/RelValTTbar_13/CMSSW_10_2_0*realistic*/GEN-SIM-*&instance=prod/global&amp;idx=50&&amp;limit=100

## Automated - DQMIO
https://cmsweb.cern.ch/dqm/relval/
- click on Summary (under Workspace) and choose MC HLT;
- click on the Run Number (to the right from Summary);
- put a sample name in the Search field (you need a DQMIO sample; find it in DAS, for example https://cmsweb.cern.ch/das/request?view=list&limit=50&instance=prod%2Fglobal&input=dataset%3D%2FRelValTTbar_13%2F*9_3_0_pre5*2017*%2FDQMIO);
- choose Vary by: Any (to the right from the Search field);
- click on the sample name which appears on the screen;
- go to HLT/BTag/Discriminator/<trigger-name>/efficiency to see the efficiency histograms;
- click View details in the upright corner;
- put a second sample name (which you want to compare) in the first Dataset field;
- choose Show reference: For all;
- click View details again;

Original TWIKI:
https://twiki.cern.ch/twiki/bin/viewauth/CMS/BtagHLTValidation


## Manual Validation
```
cmsrel CMSSW_10_2_0  # or whatever is laters
cd CMSSW_10_2_0/src
cmsenv
git cms-addpkg HLTriggerOffline/Btag
scram b -j4
cd HLTriggerOffline/Btag/test

cmsRun testSequences.py [dataset name]
# for example: 
#cmsRun testSequences.py /RelValTTbar_13/CMSSW_10_2_0-102X_upgrade2018_realistic_v9_gcc7-v1/GEN-SIM-DIGI-RAW 
```
