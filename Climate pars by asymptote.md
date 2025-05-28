
data_pars <- data_pars_options(colnames(data))[["environment"]]
 [1] "indig"             "protec"            "cec"              
 [4] "clay"              "cfvo"              "nitro"            
 [7] "ocd"               "ocs"               "phh2o"            
[10] "sand"              "soc"               "floodable_forests"
[13] "mean_pr"           "mean_srad"         "mean_temp"        
[16] "mean_vpd"          "mean_soil"         "mean_aet"         
[19] "mean_def"          "mean_pdsi"         "ecoreg_473"       
[22] "ecoreg_474"        "ecoreg_476"        "ecoreg_480"       
[25] "ecoreg_481"        "ecoreg_482"        "ecoreg_496"       
[28] "ecoreg_497"        "ecoreg_505"        "ecoreg_507"       
[31] "ecoreg_508"        "ecoreg_511"        "ecoreg_518"       
[34] "ecoreg_529"        "ecoreg_540"        "ecoreg_567"       
[37] "ecoreg_570"        "topography_21"     "topography_24"    
[40] "topography_31"     "topography_34"     "topography_41"    
[43] "topography_42"    




Asymptote: quarter_biomass 
R²: 0.2944702 
Parameters:
        indig         phh2o       mean_pr     mean_srad     mean_temp 
 0.0022872764 -0.0227926199  0.0001717466 -0.0154371448 -0.0055455289 
    mean_soil      mean_aet     mean_pdsi    ecoreg_473    ecoreg_474 
 0.0006772511 -0.0026371119  0.0014267920 -0.0001103936  0.0035761294 
   ecoreg_476    ecoreg_480    ecoreg_481    ecoreg_482    ecoreg_496 
 0.0028494075  0.0031964220  0.0017432577 -0.0018779089  0.0069118781 
   ecoreg_497    ecoreg_505    ecoreg_507    ecoreg_508    ecoreg_511 
-0.0019083821  4.6072852937  0.0099704034  0.0050869582  0.0056424506 
   ecoreg_518    ecoreg_529    ecoreg_540    ecoreg_567    ecoreg_570 
 0.0052696482  0.0029825636  0.0079722664  0.0022623279  0.0043503827 
           k0           lag 
 0.0327976922 46.0361033377 



Asymptote: ecoreg_biomass 
R²: 0.2857626 
Parameters:
        indig         phh2o     mean_srad     mean_temp      mean_aet 
 7.035868e-04 -3.112688e-02 -5.790475e-03 -1.480091e-02 -1.197808e-03 
   ecoreg_473    ecoreg_474    ecoreg_476    ecoreg_480    ecoreg_481 
 1.068295e-02  4.658193e-03  4.517735e-03  1.021856e-02  5.620756e-03 
   ecoreg_482    ecoreg_496    ecoreg_497    ecoreg_505    ecoreg_507 
 3.730021e-03  9.565616e-03  4.325385e-03  2.384036e+00  1.306163e-02 
   ecoreg_508    ecoreg_511    ecoreg_518    ecoreg_529    ecoreg_540 
 9.093819e-03  5.376535e-03  6.963072e-03  1.547082e-02  1.978705e+00 
   ecoreg_567    ecoreg_570 topography_21 topography_24 topography_31 
 1.595111e-02  5.320672e-03  5.137497e-04  1.729334e-03  1.213131e-03 
topography_34 topography_41 topography_42            k0           lag 
 9.172647e-05  2.245715e-03  3.080161e-03  3.828344e-02  4.119464e+01 




Asymptote: nearest_mature 
R²: 0.3821066 
Parameters:
          ocd         phh2o     mean_temp      mean_vpd      mean_aet 
 0.0132733469 -0.0355186858 -0.0042464668  0.0040086116 -0.0329303117 
   ecoreg_473    ecoreg_474    ecoreg_476    ecoreg_480    ecoreg_481 
-0.0032774054 -0.0059368230 -0.0077576586 -0.0075653010 -0.0035651446 
   ecoreg_482    ecoreg_496    ecoreg_497    ecoreg_505    ecoreg_507 
-0.0111496472 -0.0004668923 -0.0082613666  0.0168469588 -0.0022235607 
   ecoreg_508    ecoreg_511    ecoreg_518    ecoreg_529    ecoreg_540 
 0.0083417860 -0.0019880275 -0.0027510217 -0.0007888593 -0.0065031664 
   ecoreg_567    ecoreg_570 topography_21 topography_24 topography_31 
-0.0019412368 -0.0068893455 -0.0038969303 -0.0004988302 -0.0025240312 
topography_34 topography_41 topography_42            k0           lag 
-0.0027045925  0.0014555383  0.0038513737  0.0668914816 24.6801852589 

# --------------------------------------------------------------------

data_pars <- c("mean_srad", "mean_soil", "mean_temp", "mean_vpd", "mean_aet", "mean_def", "mean_pr", "mean_pdsi")

# ---------------- 2 replicates with the quarter_biomass

Asymptote: quarter_biomass 
R²: 0.2320623 
Parameters:
   mean_srad    mean_soil     mean_aet     mean_def      mean_pr           k0 
-0.010576624  0.005236405 -0.014025741 -0.020317557  0.003749474  0.032826708 
         lag 
47.860979019 

Asymptote: quarter_biomass 
R²: 0.2442781 
Parameters:
   mean_srad    mean_soil     mean_aet     mean_def      mean_pr           k0 
-0.011822106  0.003863935 -0.016075744 -0.023355948  0.003540806  0.038426625 
         lag 
40.983245060 

# ---------------- 2 replicates with the ecoreg_biomass

Asymptote: ecoreg_biomass 
R²: 0.256046 
Parameters:
   mean_srad    mean_soil    mean_temp     mean_vpd     mean_aet     mean_def 
-0.017274624  0.005960344 -0.020963822 -0.001179662 -0.006926335 -0.010869989 
     mean_pr           k0          lag 
 0.016108977  0.045252768 37.486690734 

Asymptote: ecoreg_biomass 
R²: 0.2466516 
Parameters:
   mean_srad    mean_soil    mean_temp     mean_vpd     mean_def      mean_pr 
-0.019818066  0.005960795 -0.023940653 -0.003219521 -0.006162354  0.012108156 
          k0          lag 
 0.044438429 41.440994677 


# ---------------- 2 replicates with the nearest_mature

Asymptote: nearest_mature 
R²: 0.3683043 
Parameters:
  mean_srad   mean_temp   mean_pdsi          k0         lag 
-0.02645459 -0.03650752  0.01036196  0.07415369 24.76192135 

Asymptote: nearest_mature 
R²: 0.3767701 
Parameters:
  mean_srad   mean_temp   mean_pdsi          k0         lag 
-0.02887013 -0.04392431  0.01219535  0.08046650 24.33869533 






