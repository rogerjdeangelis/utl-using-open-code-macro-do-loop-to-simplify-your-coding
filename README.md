# utl-using-open-code-macro-do-loop-to-simplify-your-coding
Using open code macro do loop to simplify your coding.
    Using open code macro do loop to simplify your coding

    github
    https://tinyurl.com/yauv8x4e
    https://github.com/rogerjdeangelis/utl-using-open-code-macro-do-loop-to-simplify-your-coding

    macros
    https://tinyurl.com/y9nfugth
    https://github.com/rogerjdeangelis/utl-macros-used-in-many-of-rogerjdeangelis-repositories


    SAS Forum
    https://communities.sas.com/t5/SAS-Procedures/Partial-proc-format/m-p/523140


    PROBLEM : I need to run proc format with these values
    ======================================================

    "readmission_5_arm_1"="Readmit 1"
    "readmission_6_arm_1"="Readmit 2"
    "readmission_7_arm_1"="Readmit 3"
    "readmission_8_arm_1"="Readmit 4"
    "readmission_5_arm_1"="Readmit 5"
    "readmission_6_arm_1"="Readmit 6"
    "readmission_7_arm_1"="Readmit 7"
    "readmission_8_arm_1"="Readmit 8"
    "readmission_9_arm_1"="Readmit 9"
    "readmission_10_arm_1"="Readmit 10"
    "readmission_11_arm_1"="Readmit 11"
    "readmission_12_arm_1"="Readmit 12"
    "readmission_13_arm_1"="Readmit 13"
    "readmission_14_arm_1"="Readmit 14"
    "readmission_15_arm_1"="Readmit 15"
    "readmission_16_arm_1"="Readmit 16"
    "readmission_17_arm_1"="Readmit 17"
    "readmission_18_arm_1"="Readmit 18"
    "readmission_19_arm_1"="Readmit 19"
    "readmission_20_arm_1"="Readmit 20"
    "readmission_21_arm_1"="Readmit 21"
    "readmission_22_arm_1"="Readmit 22"
    "readmission_23_arm_1"="Readmit 23"
    "readmission_24_arm_1"="Readmit 24"
    "readmission_25_arm_1"="Readmit 25"
    "readmission_26_arm_1"="Readmit 26"
    "readmission_27_arm_1"="Readmit 27"
    "readmission_28_arm_1"="Readmit 28"
    "readmission_29_arm_1"="Readmit 29"
    "readmission_30_arm_1"="Readmit 30"


    SOLUTION
    ========

    %utlopts; * turn everthing on - not needed if you have symbolgen, macrogen turned on;

    %array(idx,values=1-30);

    proc format;
      value $event_name
      %do_over(idx,phrase=%str(
             "readmission_?_arm_1"="Readmit ?"
      ));

    run;quit;

    NOTE: Format $EVENT_NAME has been output.
    202   run;

    /*

    You don't need to do this, however your production team may want the static code.
    The do_over is more fexible if there is a change.

    You need 1908s classic editor.
      1. Copy values in log window to 1980s classic program editor
      2. On clean command line(not EE command bar) type 'bounds 1 40
      3. Type 'tf' in the prefix area. This will give you the code below
    */

    OUTPUT
    ======

    "readmission_5_arm_1"="Readmit 1"
    "readmission_6_arm_1"="Readmit 2"
    "readmission_7_arm_1"="Readmit 3"
    "readmission_8_arm_1"="Readmit 4"
    "readmission_5_arm_1"="Readmit 5"
    "readmission_6_arm_1"="Readmit 6"
    "readmission_7_arm_1"="Readmit 7"
    "readmission_8_arm_1"="Readmit 8"
    "readmission_9_arm_1"="Readmit 9"
    "readmission_10_arm_1"="Readmit 10"
    "readmission_11_arm_1"="Readmit 11"
    "readmission_12_arm_1"="Readmit 12"
    "readmission_13_arm_1"="Readmit 13"
    "readmission_14_arm_1"="Readmit 14"
    "readmission_15_arm_1"="Readmit 15"
    "readmission_16_arm_1"="Readmit 16"
    "readmission_17_arm_1"="Readmit 17"
    "readmission_18_arm_1"="Readmit 18"
    "readmission_19_arm_1"="Readmit 19"
    "readmission_20_arm_1"="Readmit 20"
    "readmission_21_arm_1"="Readmit 21"
    "readmission_22_arm_1"="Readmit 22"
    "readmission_23_arm_1"="Readmit 23"
    "readmission_24_arm_1"="Readmit 24"
    "readmission_25_arm_1"="Readmit 25"
    "readmission_26_arm_1"="Readmit 26"
    "readmission_27_arm_1"="Readmit 27"
    "readmission_28_arm_1"="Readmit 28"
    "readmission_29_arm_1"="Readmit 29"
    "readmission_30_arm_1"="Readmit 30"



