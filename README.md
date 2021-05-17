# SampleScripts
Sample scripts for 20 GeV e- events production

git clone it in the <install-dir>  and follow below
    
# Job Submission

    cd SampleScripts/submission
    cp * <install-dir>
    cd <install-dir>
    vi executable.sh (change <filename>)
    condor_submit submit.sub
  
You can check job status via

    condor_q or condor_q -all


# Analyzing

    cd SampleScripts/analyzing
    cp calib.csv ../../../Reco
    cp analysis.cc ../../../analysis
    cp init_lcg_install.sh ../../
    cd ../../../build
    make -j4 install
    cd ../install
    source init_lcg_install.sh
    hadd <output_filename> <input_files>
    ./bin/analysis output_filename <low> <high>
