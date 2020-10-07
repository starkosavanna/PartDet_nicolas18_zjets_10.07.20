# PartDet Folder Files for 2018
* Notes
  * These are the PartDet files for 2018.
  * Instead of copying all of the files, I thought I'd just mention which changes I made to the files in the folder in the 
  directory above this, PartDet_2016.

1. Changes to Files in PartDet_2016
   1. I plan to begin with CR B.
   1. Therefore, in DiParticle_info.in, I'll leave the DiscrByOSLSType to OS.
   1. I'll be running MET < 30 GeV (assuming that's the number I get from my MET Optimization study).
   1. Therefore, in Run_info.in, I'll set  
   DiscrByMet true  
   MetCut 0.0 30.0
   1. Additionally, in Run_info.in, I'd change the trigger to:
      1. HLT_DoubleMediumCombinedIsoPFTau
   1. Additionally, in Jet_info.in, I'd change the following:
      1. Every instance of ApplyLooseID 1 --> ApplyLooseID 0 and ApplyTightID 0 --> ApplyTightID 1
      1. The JetBTagging requirement would change from CSVv2 --> DeepCSV
      1. The JetBTaggingCut requirement would change from 0.8484 --> 0.4184
   1. These files are for the general SAMPLES_LIST_M_BINNED_2018_nanoAOD.txt.  The other two sample lists I have for 2018 are:
      1. SAMPLES_LIST_M_BINNED_2018_nanoAOD_DY+Jets_0to100.txt
      1. SAMPLES_LIST_M_BINNED_2018_nanoAOD_W+Jets_0to70.txt

The only other changes I'd make to the PartDet files is that in the sample list making up for 0 to 100 for DY+Jet, in Run_info.in I'd do:  
/// --- dilepton mass filter --- ///  
DiscrByGenDileptonMass true  
GenDilepMassRange 0 100.0  
And then for the sample list making up for 0 to 70 for W+Jet, in Run_info.in I'd do:  
/// --- HT filter --- ///  
DiscrByGenHT true  
LowerGenHtCut 0.0  
UpperGenHtCut 70.0  
