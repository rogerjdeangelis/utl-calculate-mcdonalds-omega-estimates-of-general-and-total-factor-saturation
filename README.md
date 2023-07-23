# utl-calculate-mcdonalds-omega-estimates-of-general-and-total-factor-saturation
Calculate McDonald's omega estimates of general and total factor saturation 
    %let pgm=utl-calculate-mcdonalds-omega-estimates-of-general-and-total-factor-saturation;

    Calculate McDonald's omega estimates of general and total factor saturation

    github
    https://tinyurl.com/2p85ncc5
    https://github.com/rogerjdeangelis/utl-calculate-mcdonalds-omega-estimates-of-general-and-total-factor-saturation

    Omega in R with bells and whistles
    https://www.personality-project.org/r/html/omega.html

    SOAPBOX ON
      The problem I have with R and more so with Python is intergrating the output
      with other languages, see the 17 list objects below in the Omega list output.
      I converted just one of the 17 to a WPS/SAS dataset.
      Too many datatypes and too many data structures?
    SOAPBOX OFF

    I am not that knowlegeable of Omega statistics

    Stackoverflow SAS
    https://stackoverflow.com/questions/76708856/mcdonalds-omega-in-sas

    There is a sas macro
    Hayes, A. F., & Coutts, J. J. (2020). Use omega rather than Cronbach's alpha for estimating reliability.
    But...  Communication Methods and Measures, 14, 1-24. [PDF]


    /*                   _
    (_)_ __  _ __  _   _| |_
    | | `_ \| `_ \| | | | __|
    | | | | | |_) | |_| | |_
    |_|_| |_| .__/ \__,_|\__|
            |_|
    */

    libname sd1 "d:/sd1";

    data sd1.have;informat
    VISUALPERCEPTION 8.
    CUBES 8.
    PAPERFORMBOARD 8.
    FLAGS 8.
    GENERALINFORMATION 8.
    PARGRAPHCOMPREHENSION 8.
    SENTENCECOMPLETION 8.
    WORDCLASSIFICATION 8.
    WORDMEANING 8.
    ADDITION 8.
    CODE 8.
    COUNTINGDOTS 8.
    STRAIGHTCURVEDCAPITALS 8.
    WORDRECOGNITION 8.
    NUMBERRECOGNITION 8.
    FIGURERECOGNITION 8.
    OBJECTNUMBER 8.
    NUMBERFIGURE 8.
    FIGUREWORD 8.
    DEDUCTION 8.
    NUMERICALPUZZLES 8.
    PROBLEMREASONING 8.
    SERIESCOMPLETION 8.
    ARITHMETICPROBLEMS 8.
    ;input
    VISUALPERCEPTION CUBES PAPERFORMBOARD FLAGS GENERALINFORMATION PARGRAPHCOMPREHENSION SENTENCECOMPLETION
    WORDCLASSIFICATION WORDMEANING ADDITION CODE COUNTINGDOTS STRAIGHTCURVEDCAPITALS WORDRECOGNITION
    NUMBERRECOGNITION FIGURERECOGNITION OBJECTNUMBER NUMBERFIGURE FIGUREWORD
    DEDUCTION NUMERICALPUZZLES PROBLEMREASONING SERIESCOMPLETION ARITHMETICPROBLEMS;
    cards4;
    1 .318 .403 .468 .321 .335 .304 .332 .326 .116 .308 .314 .489 .125 .238 .414 .176 .368 .27 .365 .369 .413 .474 .282
    .318 1 .317 .23 .285 .234 .157 .157 .195 .057 .15 .145 .239 .103 .131 .272 .005 .255 .112 .292 .306 .232 .348 .211
    .403 .317 1 .305 .247 .268 .223 .382 .184 -.075 .091 .14 .321 .177 .065 .263 .177 .211 .312 .297 .165 .25 .383 .203
    .468 .23 .305 1 .227 .327 .335 .391 .325 .099 .11 .16 .327 .066 .127 .322 .187 .251 .137 .339 .349 .38 .335 .248
    .321 .285 .247 .227 1 .622 .656 .578 .723 .311 .344 .215 .344 .28 .229 .187 .208 .263 .19 .398 .318 .441 .435 .42
    .335 .234 .268 .327 .622 1 .722 .527 .714 .203 .353 .095 .309 .292 .251 .291 .273 .167 .251 .435 .263 .386 .431 .433
    .304 .157 .223 .335 .656 .722 1 .619 .685 .246 .232 .181 .345 .236 .172 .18 .228 .159 .226 .451 .314 .396 .405 .437
    .332 .157 .382 .391 .578 .527 .619 1 .532 .285 .3 .271 .395 .252 .175 .296 .255 .25 .274 .427 .362 .357 .501 .388
    .326 .195 .184 .325 .723 .714 .685 .532 1 .17 .28 .113 .28 .26 .248 .242 .274 .208 .274 .446 .266 .483 .504 .424
    .116 .057 -.075 .099 .311 .203 .246 .285 .17 1 .484 .585 .408 .172 .154 .124 .289 .317 .19 .173 .405 .16 .262 .531
    .308 .15 .091 .11 .344 .353 .232 .3 .28 .484 1 .428 .535 .35 .24 .314 .362 .35 .29 .202 .399 .304 .251 .412
    .314 .145 .14 .16 .215 .095 .181 .271 .113 .585 .428 1 .512 .131 .173 .119 .278 .349 .11 .246 .355 .193 .35 .414
    .489 .239 .321 .327 .344 .309 .345 .395 .28 .408 .535 .512 1 .195 .139 .281 .194 .323 .263 .241 .425 .279 .382 .358
    .125 .103 .177 .066 .28 .292 .236 .252 .26 .172 .35 .131 .195 1 .37 .412 .341 .201 .206 .302 .183 .243 .242 .304
    .238 .131 .065 .127 .229 .251 .172 .175 .248 .154 .24 .173 .139 .37 1 .325 .345 .334 .192 .272 .232 .246 .256 .165
    .414 .272 .263 .322 .187 .291 .18 .296 .242 .124 .314 .119 .281 .412 .325 1 .324 .344 .258 .388 .348 .283 .36 .262
    .176 .005 .177 .187 .208 .273 .228 .255 .274 .289 .362 .278 .194 .341 .345 .324 1 .448 .324 .262 .173 .273 .287 .326
    .368 .255 .211 .251 .263 .167 .159 .25 .208 .317 .35 .349 .323 .201 .334 .344 .448 1 .358 .301 .357 .317 .272 .405
    .27 .112 .312 .137 .19 .251 .226 .274 .274 .19 .29 .11 .263 .206 .192 .258 .324 .358 1 .167 .331 .342 .303 .374
    .365 .292 .297 .339 .398 .435 .451 .427 .446 .173 .202 .246 .241 .302 .272 .388 .262 .301 .167 1 .413 .463 .509 .366
    .369 .306 .165 .349 .318 .263 .314 .362 .266 .405 .399 .355 .425 .183 .232 .348 .173 .357 .331 .413 1 .374 .451 .448
    .413 .232 .25 .38 .441 .386 .396 .357 .483 .16 .304 .193 .279 .243 .246 .283 .273 .317 .342 .463 .374 1 .503 .375
    .474 .348 .383 .335 .435 .431 .405 .501 .504 .262 .251 .35 .382 .242 .256 .36 .287 .272 .303 .509 .451 .503 1 .434
    .282 .211 .203 .248 .42 .433 .437 .388 .424 .531 .412 .414 .358 .304 .165 .262 .326 .405 .374 .366 .448 .375 .434 1
    ;;;;
    run;quit;

    /**************************************************************************************************************************/
    /*                           _                                        _        _                                          */
    /*   ___ _____   ____ _ _ __(_) __ _ _ __   ___ ___   _ __ ___   __ _| |_ _ __(_)_  __                                    */
    /*  / __/ _ \ \ / / _` | `__| |/ _` | `_ \ / __/ _ \ | `_ ` _ \ / _` | __| `__| \ \/ /                                    */
    /* | (_| (_) \ V / (_| | |  | | (_| | | | | (_|  __/ | | | | | | (_| | |_| |  | |>  <                                     */
    /*  \___\___/ \_/ \__,_|_|  |_|\__,_|_| |_|\___\___| |_| |_| |_|\__,_|\__|_|  |_/_/\_\                                    */
    /*                                                                                                                        */
    /*                                                                                                                        */
    /*  Middle Observation(12 ) of table = sd1.have - Total Obs 24                                                            */
    /*                                                                                                                        */
    /*   -- NUMERIC --                                                                                                        */
    /*  VISUALPERCEPTION                 N8           0.314                                                                   */
    /*  CUBES                            N8           0.145                                                                   */
    /*  PAPERFORMBOARD                   N8            0.14                                                                   */
    /*  FLAGS                            N8            0.16                                                                   */
    /*  GENERALINFORMATION               N8           0.215                                                                   */
    /*  PARGRAPHCOMPREHENSION            N8           0.095                                                                   */
    /*  SENTENCECOMPLETION               N8           0.181                                                                   */
    /*  WORDCLASSIFICATION               N8           0.271                                                                   */
    /*  WORDMEANING                      N8           0.113                                                                   */
    /*  ADDITION                         N8           0.585                                                                   */
    /*  CODE                             N8           0.428                                                                   */
    /*  COUNTINGDOTS                     N8               1                                                                   */
    /*  STRAIGHTCURVEDCAPITALS           N8           0.512                                                                   */
    /*  WORDRECOGNITION                  N8           0.131                                                                   */
    /*  NUMBERRECOGNITION                N8           0.173                                                                   */
    /*  FIGURERECOGNITION                N8           0.119                                                                   */
    /*  OBJECTNUMBER                     N8           0.278                                                                   */
    /*  NUMBERFIGURE                     N8           0.349                                                                   */
    /*  FIGUREWORD                       N8            0.11                                                                   */
    /*  DEDUCTION                        N8           0.246                                                                   */
    /*  NUMERICALPUZZLES                 N8           0.355                                                                   */
    /*  PROBLEMREASONING                 N8           0.193                                                                   */
    /*  SERIESCOMPLETION                 N8            0.35                                                                   */
    /*  ARITHMETICPROBLEMS               N8           0.414                                                                   */
    /*                                                                                                                        */
    /*                                                                                                                        */
    /**************************************************************************************************************************/

    /*           _               _
      ___  _   _| |_ _ __  _   _| |_
     / _ \| | | | __| `_ \| | | | __|
    | (_) | |_| | |_| |_) | |_| | |_
     \___/ \__,_|\__| .__/ \__,_|\__|
                    |_|
    */

    /**************************************************************************************************************************/
    /*                                                                                                                        */
    /* The WPS System SD1.WANT DATASET                                                                                        */
    /*                                                                                                                        */
    /* Obs    STATISTIC              VALUE                                                                                    */
    /*                                                                                                                        */
    /*  1     ALPHA                 0.64349                                                                                   */
    /*  2     G6                    0.69273                                                                                   */
    /*  3     OMEGA_HIERARCHICAL    0.91188                                                                                   */
    /*  4     OMEGA_HASYMPTOTIC     0.92891                                                                                   */
    /*  5     OMEGA_TOTAL           0.93664                                                                                   */
    /*                                                                                                                        */
    /**************************************************************************************************************************/
    /*                                                                                                                        */
    /* PRINTED OUTPUT                                                                                                         */
    /*                                                                                                                        */
    /*  Call: omegah(m = m, nfactors = nfactors, fm = fm, key = key, flip = flip,                                             */
    /*      digits = digits, title = title, sl = sl, labels = labels,                                                         */
    /*      plot = plot, n.obs = n.obs, rotate = rotate, Phi = Phi, option = option,                                          */
    /*      covar = covar)                                                                                                    */
    /*                                                                                                                        */
    /*  Alpha:                 0.91                                                                                           */
    /*  G.6:                   0.94                                                                                           */
    /*  Omega Hierarchical:    0.64                                                                                           */
    /*  Omega H asymptotic:    0.69                                                                                           */
    /*  Omega Total            0.93                                                                                           */
    /*                                                                                                                        */
    /*  Schmid Leiman Factor loadings greater than  0.2                                                                       */
    /*                            g   F1*   F2*   F3*   h2   u2   p2                                                          */
    /*  VISUALPERCEPTION       0.52        0.47       0.49 0.51 0.54                                                          */
    /*  CUBES                  0.33        0.31       0.21 0.79 0.51                                                          */
    /*  PAPERFORMBOARD         0.38        0.39       0.33 0.67 0.43                                                          */
    /*  FLAGS                  0.42        0.34       0.31 0.69 0.57                                                          */
    /*  GENERALINFORMATION     0.57  0.55             0.64 0.36 0.51                                                          */
    /*  PARGRAPHCOMPREHENSION  0.57  0.58             0.67 0.33 0.49                                                          */
    /*  SENTENCECOMPLETION     0.56  0.63             0.72 0.28 0.44                                                          */
    /*  WORDCLASSIFICATION     0.56  0.40             0.50 0.50 0.64                                                          */
    /*  WORDMEANING            0.58  0.63             0.74 0.26 0.46                                                          */
    /*  ADDITION               0.35              0.78 0.74 0.26 0.16                                                          */
    /*  CODE                   0.44              0.50 0.46 0.54 0.42                                                          */
    /*  COUNTINGDOTS           0.36              0.56 0.47 0.53 0.28                                                          */
    /*  STRAIGHTCURVEDCAPITALS 0.49        0.25  0.34 0.42 0.58 0.57                                                          */
    /*  WORDRECOGNITION        0.34                   0.17 0.83 0.68                                                          */
    /*  NUMBERRECOGNITION      0.32        0.20       0.16 0.84 0.64                                                          */
    /*  FIGURERECOGNITION      0.44        0.42       0.37 0.63 0.52                                                          */
    /*  OBJECTNUMBER           0.37              0.27 0.24 0.76 0.57                                                          */
    /*  NUMBERFIGURE           0.43        0.33  0.30 0.39 0.61 0.47                                                          */
    /*  FIGUREWORD             0.37        0.24       0.22 0.78 0.64                                                          */
    /*  DEDUCTION              0.53  0.23  0.29       0.42 0.58 0.67                                                          */
    /*  NUMERICALPUZZLES       0.49        0.29  0.28 0.41 0.59 0.60                                                          */
    /*  PROBLEMREASONING       0.52  0.22  0.28       0.40 0.60 0.68                                                          */
    /*  SERIESCOMPLETION       0.59  0.21  0.34       0.50 0.50 0.68                                                          */
    /*  ARITHMETICPROBLEMS     0.53  0.20        0.40 0.49 0.51 0.56                                                          */
    /*                                                                                                                        */
    /*  With Sums of squares  of:                                                                                             */
    /*    g F1* F2* F3*                                                                                                       */
    /*  5.3 1.8 1.5 1.8                                                                                                       */
    /*                                                                                                                        */
    /*  general/max  2.87   max/min =   1.21                                                                                  */
    /*  mean percent general =  0.53    with sd =  0.13 and cv of  0.24                                                       */
    /*  Explained Common Variance of the general factor =  0.51                                                               */
    /*                                                                                                                        */
    /*  The degrees of freedom are 207  and the fit is  2.24                                                                  */
    /*                                                                                                                        */
    /*  The root mean square of the residuals is  0.05                                                                        */
    /*  The df corrected root mean square of the residuals is  0.06                                                           */
    /*                                                                                                                        */
    /*  Compare this with the adequacy of just a general factor and no group factors                                          */
    /*  The degrees of freedom for just the general factor are 252  and the fit is  4.96                                      */
    /*                                                                                                                        */
    /*  The root mean square of the residuals is  0.13                                                                        */
    /*  The df corrected root mean square of the residuals is  0.14                                                           */
    /*                                                                                                                        */
    /*  Measures of factor score adequacy                                                                                     */
    /*                                                   g  F1*   F2*  F3*                                                    */
    /*  Correlation of scores with factors            0.81 0.78  0.70 0.86                                                    */
    /*  Multiple R square of scores with factors      0.65 0.61  0.49 0.74                                                    */
    /*  Minimum correlation of factor score estimates 0.31 0.22 -0.02 0.48                                                    */
    /*                                                                                                                        */
    /*   Total, General and Subset omega for each subset                                                                      */
    /*                                                   g  F1*  F2*  F3*                                                     */
    /*  Omega total for total scores and subscales    0.93 0.90 0.82 0.80                                                     */
    /*  Omega general for total scores and subscales  0.64 0.46 0.55 0.35                                                     */
    /*  Omega group for total scores and subscales    0.17 0.44 0.28 0.44                                                     */
    /*                                                                                                                        */
    /**************************************************************************************************************************/

    /*         _       _   _
     ___  ___ | |_   _| |_(_) ___  _ __
    / __|/ _ \| | | | | __| |/ _ \| `_ \
    \__ \ (_) | | |_| | |_| | (_) | | | |
    |___/\___/|_|\__,_|\__|_|\___/|_| |_|

    */

    /*
    DEFAULT VALUES

    Call: omegah(m = m, nfactors = nfactors, fm = fm, key = key, flip = flip,
        digits = digits, title = title, sl = sl, labels = labels,
        plot = plot, n.obs = n.obs, rotate = rotate, Phi = Phi, option = option,
        covar = covar)
    */

    %utl_submit_wps64x('
    libname sd1 "d:/sd1";
    proc r;
    export data=sd1.have r=have;
    submit;
    library(psych);
    library(GPArotation);
    lst <- omega(have);
    str(lst);
    sink("d:/txt/genstat.txt");
    print(lst,digits=2);
    sink();
    genstat<-as.data.frame(cbind(
        lst$omega_h
       ,lst$omega.lim
       ,lst$alpha
       ,lst $omega.tot
       ,lst$G6
       ));
    colnames(genstat)=c(
       "Alpha"
       ,"G6"
       ,"Omega_Hierarchical"
       ,"Omega_Hasymptotic"
       ,"Omega_Total"
       );
    endsubmit;
    import data=sd1.genstat r=genstat;
    run;quit;
    proc transpose data=sd1.genstat out=sd1.want (rename=(_name_=Statistic col1=Value));
    run;quit;
    proc print;
    run;quit;
    ');

     /*
    (_)___ ___ _   _  ___
    | / __/ __| | | |/ _ \
    | \__ \__ \ |_| |  __/
    |_|___/___/\__,_|\___|

    */

    /**************************************************************************************************************************/
    /*                                                                                                                        */
    /* EASIER TO PARSE THE PRINTED OUTPUT                                                                                     */
    /*                                                                                                                        */
    /* The WPS System                                                                                                         */
    /*                                                                                                                        */
    /* List of 17                                                                                                             */
    /*  $ omega_h    : num 0.643                                                                                              */
    /*  $ omega.lim  : num 0.693                                                                                              */
    /*  $ alpha      : num 0.912                                                                                              */
    /*  $ omega.tot  : num 0.929                                                                                              */
    /*  $ G6         : num 0.937                                                                                              */
    /*  $ schmid     :List of 17                                                                                              */
    /*   ..$ sl       : num [1:24, 1:7] 0.517 0.327 0.376 0.421 0.568 ...                                                     */
    /*   .. ..- attr(*, "dimnames")=List of 2                                                                                 */
    /*   .. .. ..$ : chr [1:24] "VISUALPERCEPTION" "CUBES" "PAPERFORMBOARD" "FLAGS" ...                                       */
    /*   .. .. ..$ : chr [1:7] "g" "F1*" "F2*" "F3*" ...                                                                      */
    /*   ..$ orthog   : 'loadings' num [1:24, 1:3] 0.169 0.121 0.159 0.24 0.737 ...                                           */
    /*   .. ..- attr(*, "dimnames")=List of 2                                                                                 */
    /*   .. .. ..$ : chr [1:24] "VISUALPERCEPTION" "CUBES" "PAPERFORMBOARD" "FLAGS" ...                                       */
    /*   .. .. ..$ : chr [1:3] "F1" "F2" "F3"                                                                                 */
    /*   ..$ oblique  : num [1:24, 1:3] 0.0224 0.0343 0.0673 0.1566 0.7608 ...                                                */
    /*   .. ..- attr(*, "dimnames")=List of 2                                                                                 */
    /*   .. .. ..$ : chr [1:24] "VISUALPERCEPTION" "CUBES" "PAPERFORMBOARD" "FLAGS" ...                                       */
    /*   .. .. ..$ : chr [1:3] "F1" "F2" "F3"                                                                                 */
    /*   ..$ phi      : num [1:3, 1:3] 1 0.502 0.324 0.502 1 ...                                                              */
    /*   .. ..- attr(*, "dimnames")=List of 2                                                                                 */
    /*   .. .. ..$ : chr [1:3] "F1" "F2" "F3"                                                                                 */
    /*   .. .. ..$ : chr [1:3] "F1" "F2" "F3"                                                                                 */
    /*   ..$ gloading : 'loadings' num [1:3, 1] 0.686 0.731 0.472                                                             */
    /*   .. ..- attr(*, "dimnames")=List of 2                                                                                 */
    /*   .. .. ..$ : chr [1:3] "F1" "F2" "F3"                                                                                 */
    /*   .. .. ..$ : chr "MR1"                                                                                                */
    /*   ..$ dof      : num 207                                                                                               */
    /*   ..$ objective: Named num 2.24                                                                                        */
    /*   .. ..- attr(*, "names")= chr "objective"                                                                             */
    /*   ..$ STATISTIC: NULL                                                                                                  */
    /*   ..$ PVAL     : logi NA                                                                                               */
    /*   ..$ RMSEA    : NULL                                                                                                  */
    /*   ..$ BIC      : NULL                                                                                                  */
    /*   ..$ rms      : num 0.0547                                                                                            */
    /*   ..$ crms     : num 0.0632                                                                                            */
    /*   ..$ n.obs    : logi NA                                                                                               */
    /*   ..$ scores   : NULL                                                                                                  */
    /*   ..$ S.Phi    : num [1:4, 1:4] 0.699 0.284 0.322 0.161 0.284 ...                                                      */
    /*   ..$ Call     : language schmid(model = m, nfactors = nfactors, fm = fm, digits = digits,                             */
    /*                  rotate = rotate, n.obs = n.obs, option = option,| __truncated__                                       */
    /*   ..- attr(*, "class")= chr [1:2] "psych" "schmid"                                                                     */
    /*  $ key        : Named num [1:24] 1 1 1 1 1 1 1 1 1 1 ...                                                               */
    /*   ..- attr(*, "names")= chr [1:24] "VISUALPERCEPTION" "CUBES" "PAPERFORMBOARD" "FLAGS" ...                             */
    /*  $ stats      :List of 27                                                                                              */
    /*   ..$ residual  : num [1:24, 1:24] 0.508045 0.000372 0.020278 0.088775 0.021309 ...                                    */
    /*   .. ..- attr(*, "dimnames")=List of 2                                                                                 */
    /*   .. .. ..$ : chr [1:24] "VISUALPERCEPTION" "CUBES" "PAPERFORMBOARD" "FLAGS" ...                                       */
    /*   .. .. ..$ : chr [1:24] "VISUALPERCEPTION" "CUBES" "PAPERFORMBOARD" "FLAGS" ...                                       */
    /*   ..$ dof       : num 186                                                                                              */
    /*   ..$ ENull     : num NA                                                                                               */
    /*   ..$ chi       : num NA                                                                                               */
    /*   ..$ rms       : num 0.0547                                                                                           */
    /*   ..$ nh        : logi NA                                                                                              */
    /*   ..$ EPVAL     : num NA                                                                                               */
    /*   ..$ crms      : num 0.0667                                                                                           */
    /*   ..$ EBIC      : num NA                                                                                               */
    /*   ..$ ESABIC    : num NA                                                                                               */
    /*   ..$ fit       : num 0.879                                                                                            */
    /*   ..$ fit.off   : num 0.972                                                                                            */
    /*   ..$ sd        : num 0.0536                                                                                           */
    /*   ..$ factors   : int 4                                                                                                */
    /*   ..$ complexity: Named num [1:24] 1.99 2.07 2.39 2.17 2.06 ...                                                        */
    /*   .. ..- attr(*, "names")= chr [1:24] "VISUALPERCEPTION" "CUBES" "PAPERFORMBOARD" "FLAGS" ...                          */
    /*   ..$ n.obs     : logi NA                                                                                              */
    /*   ..$ PVAL      : logi NA                                                                                              */
    /*   ..$ objective : num 2.24                                                                                             */
    /*   ..$ criteria  : Named num [1:3] 2.24 NA NA                                                                           */
    /*   .. ..- attr(*, "names")= chr [1:3] "objective" "" ""                                                                 */
    /*   ..$ Call      : language fa.stats(r = r, f = f, phi = phi, n.obs = n.obs, np.obs =                                   */
    /*                   np.obs, alpha = alpha, fm = fm, smooth = smooth)                                                     */
    /*   ..$ null.model: num 11.4                                                                                             */
    /*   ..$ null.dof  : num 276                                                                                              */
    /*   ..$ r.scores  : num [1:4, 1:4] 1 0.455 0.486 0.236 0.455 ...                                                         */
    /*   .. ..- attr(*, "dimnames")=List of 2                                                                                 */
    /*   .. .. ..$ : chr [1:4] "g" "F1*" "F2*" "F3*"                                                                          */
    /*   .. .. ..$ : chr [1:4] "g" "F1*" "F2*" "F3*"                                                                          */
    /*   ..$ R2        : Named num [1:4] 0.654 0.609 0.492 0.738                                                              */
    /*   .. ..- attr(*, "names")= chr [1:4] "g" "F1*" "F2*" "F3*"                                                             */
    /*   ..$ valid     : num [1:4] 0.783 0.686 0.392 0.751                                                                    */
    /*   ..$ score.cor : num [1:4, 1:4] 1 0.65 0.449 0.557 0.65 ...                                                           */
    /*   ..$ weights   : num [1:24, 1:4] 0.0845 0.0306 0.0625 0.0421 0.0575 ...                                               */
    /*   .. ..- attr(*, "dimnames")=List of 2                                                                                 */
    /*   .. .. ..$ : NULL                                                                                                     */
    /*   .. .. ..$ : chr [1:4] "g" "F1*" "F2*" "F3*"                                                                          */
    /*   ..- attr(*, "class")= chr [1:2] "psych" "stats"                                                                      */
    /*  $ ECV        : Named num 0.506                                                                                        */
    /*   ..- attr(*, "names")= chr "g"                                                                                        */
    /*  $ gstats     :List of 26                                                                                              */
    /*   ..$ residual  : num [1:24, 1:24] 0.7324 0.1489 0.2084 0.25 0.0271 ...                                                */
    /*   .. ..- attr(*, "dimnames")=List of 2                                                                                 */
    /*   .. .. ..$ : chr [1:24] "VISUALPERCEPTION" "CUBES" "PAPERFORMBOARD" "FLAGS" ...                                       */
    /*   .. .. ..$ : chr [1:24] "VISUALPERCEPTION" "CUBES" "PAPERFORMBOARD" "FLAGS" ...                                       */
    /*   ..$ dof       : num 252                                                                                              */
    /*   ..$ ENull     : num NA                                                                                               */
    /*   ..$ chi       : num NA                                                                                               */
    /*   ..$ rms       : num 0.133                                                                                            */
    /*   ..$ nh        : logi NA                                                                                              */
    /*   ..$ EPVAL     : num NA                                                                                               */
    /*   ..$ crms      : num 0.139                                                                                            */
    /*   ..$ EBIC      : num NA                                                                                               */
    /*   ..$ ESABIC    : num NA                                                                                               */
    /*   ..$ fit       : num 0.703                                                                                            */
    /*   ..$ fit.off   : num 0.833                                                                                            */
    /*   ..$ sd        : num 0.0987                                                                                           */
    /*   ..$ factors   : int 1                                                                                                */
    /*   ..$ complexity: Named num [1:24] 1 1 1 1 1 1 1 1 1 1 ...                                                             */
    /*   .. ..- attr(*, "names")= chr [1:24] "VISUALPERCEPTION" "CUBES" "PAPERFORMBOARD" "FLAGS" ...                          */
    /*   ..$ n.obs     : logi NA                                                                                              */
    /*   ..$ PVAL      : logi NA                                                                                              */
    /*   ..$ objective : num 4.96                                                                                             */
    /*   ..$ criteria  : Named num [1:3] 4.96 NA NA                                                                           */
    /*   .. ..- attr(*, "names")= chr [1:3] "objective" "" ""                                                                 */
    /*   ..$ Call      : language fa.stats(r = r, f = f, phi = phi, n.obs = n.obs, np.obs = np.obs, alpha = alpha, fm = fm
    /*   ..$ null.model: num 11.4                                                                                             */
    /*   ..$ null.dof  : num 276                                                                                              */
    /*   ..$ r.scores  : num [1, 1] 1                                                                                         */
    /*   ..$ R2        : num 0.654                                                                                            */
    /*   ..$ valid     : num [1, 1] 0.802                                                                                     */
    /*   ..$ weights   : num [1:24, 1] 0.0845 0.0306 0.0625 0.0421 0.0575 ...                                                 */
    /*   ..- attr(*, "class")= chr [1:2] "psych" "stats"                                                                      */
    /*  $ call       : language omegah(m = m, nfactors = nfactors, fm = fm, key = key, flip = flip, digits = digits, title =  */
    /*  $ title      : chr "Omega"                                                                                            */
    /*  $ R          : num [1:24, 1:24] 1 0.318 0.403 0.468 0.321 0.335 0.304 0.332 0.326 0.116 ...                           */
    /*   ..- attr(*, "dimnames")=List of 2                                                                                    */
    /*   .. ..$ : chr [1:24] "VISUALPERCEPTION" "CUBES" "PAPERFORMBOARD" "FLAGS" ...                                          */
    /*   .. ..$ : chr [1:24] "VISUALPERCEPTION" "CUBES" "PAPERFORMBOARD" "FLAGS" ...                                          */
    /*  $ model      :List of 2                                                                                               */
    /*   ..$ sem   : chr [1:76, 1:3] "g->VISUALPERCEPTION" "g->CUBES" "g->PAPERFORMBOARD" "g->FLAGS" ...                      */
    /*   .. ..- attr(*, "dimnames")=List of 2                                                                                 */
    /*   .. .. ..$ : NULL                                                                                                     */
    /*   .. .. ..$ : chr [1:3] "Path" "Parameter" "Initial Value"                                                             */
    /*   ..$ lavaan: 'noquote' chr [1:4] "g =~ +VISUALPERCEPTION+CUBES+PAPERFORMBOARD+FLAGS+GENERALINFORMATION+PARGRAPHCOMPREH*/
    /*  $ omega.group:'data.frame':	4 obs. of  3 variables:                                                                   */
    /*   ..$ total  : num [1:4] 0.929 0.898 0.824 0.798                                                                       */
    /*   ..$ general: num [1:4] 0.643 0.458 0.546 0.354                                                                       */
    /*   ..$ group  : num [1:4] 0.17 0.44 0.279 0.444                                                                         */
    /*  $ scores     : NULL                                                                                                   */
    /*  $ Call       : language omega(m = have)                                                                               */
    /*                                                                                                                        */
    /**************************************************************************************************************************/

    /*              _
      ___ _ __   __| |
     / _ \ `_ \ / _` |
    |  __/ | | | (_| |
     \___|_| |_|\__,_|

    */
