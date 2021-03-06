
# Working with PubMed in R

PubMed is a service that provides the option to look into the literature, papers or abstracts and so on. The service is available at<br> [PubMed](https://www.ncbi.nlm.nih.gov). R provides an interface to look into the various aspects of the literature via PubMed.<br> 
We can use the searching, storing, and mining, and quantification meta-analysis via the R without visiting the PubMed page every time.


```R
options(repos=structure(c(CRAN="https://mirrors.tuna.tsinghua.edu.cn/CRAN/")))
# at first, 'RISmed' packages should be installed.
```


```R
install.packages("RISmed")
```

    package 'RISmed' successfully unpacked and MD5 sums checked
    
    The downloaded binary packages are in
    	C:\Users\Administrator\AppData\Local\Temp\RtmpUtoOWL\downloaded_packages
    


```R
library(RISmed)
```


```R
data(myeloma)
# 'myeloma' is the default data available with the 'RISmed' package .
```


```R
str(myeloma)
# To see the contents of the 'myeloma' object
```

    Formal class 'Medline' [package "RISmed"] with 59 slots
      ..@ Query               : chr "\"multiple myeloma\"[MeSH Terms] AND 2012/05/08[EDAT] : 2013/05/08[EDAT]"
      ..@ PMID                : chr [1:10] "23648714" "23648667" "23648347" "23648290" ...
      ..@ YearReceived        : num [1:10] NA 2013 NA 2013 2013 ...
      ..@ MonthReceived       : num [1:10] NA 4 NA 4 2 NA NA 7 NA 3
      ..@ DayReceived         : num [1:10] NA 18 NA 16 3 NA NA 18 NA 4
      ..@ HourReceived        : num [1:10] NA NA NA NA NA NA NA NA NA NA
      ..@ MinuteReceived      : num [1:10] NA NA NA NA NA NA NA NA NA NA
      ..@ YearAccepted        : num [1:10] NA 2013 NA 2013 2013 ...
      ..@ MonthAccepted       : num [1:10] NA 5 NA 4 3 NA 5 3 NA 3
      ..@ DayAccepted         : num [1:10] NA 1 NA 18 18 NA 1 26 NA 4
      ..@ HourAccepted        : num [1:10] NA NA NA NA NA NA NA NA NA NA
      ..@ MinuteAccepted      : num [1:10] NA NA NA NA NA NA NA NA NA NA
      ..@ YearEpublish        : num [1:10] 2012 NA NA NA NA ...
      ..@ MonthEpublish       : num [1:10] 3 NA NA NA NA NA NA 4 NA NA
      ..@ DayEpublish         : num [1:10] 1 NA NA NA NA NA NA 30 NA NA
      ..@ HourEpublish        : num [1:10] NA NA NA NA NA NA NA NA NA NA
      ..@ MinuteEpublish      : num [1:10] NA NA NA NA NA NA NA NA NA NA
      ..@ YearPpublish        : num [1:10] NA NA NA NA NA ...
      ..@ MonthPpublish       : num [1:10] NA NA NA NA NA NA NA NA NA NA
      ..@ DayPpublish         : num [1:10] NA NA NA NA NA NA NA NA NA NA
      ..@ HourPpublish        : num [1:10] NA NA NA NA NA NA NA NA NA NA
      ..@ MinutePpublish      : num [1:10] NA NA NA NA NA NA NA NA NA NA
      ..@ YearPmc             : num [1:10] NA NA NA NA NA NA NA NA NA NA
      ..@ MonthPmc            : num [1:10] NA NA NA NA NA NA NA NA NA NA
      ..@ DayPmc              : num [1:10] NA NA NA NA NA NA NA NA NA NA
      ..@ HourPmc             : num [1:10] NA NA NA NA NA NA NA NA NA NA
      ..@ MinutePmc           : num [1:10] NA NA NA NA NA NA NA NA NA NA
      ..@ YearPubmed          : num [1:10] 2013 2013 2013 2013 2013 ...
      ..@ MonthPubmed         : num [1:10] 5 5 5 5 5 5 5 5 5 5
      ..@ DayPubmed           : num [1:10] 8 8 8 8 8 8 8 7 7 7
      ..@ HourPubmed          : num [1:10] 6 6 6 6 6 6 6 6 6 6
      ..@ MinutePubmed        : num [1:10] 0 0 0 0 0 0 0 0 0 0
      ..@ Author              :List of 10
      .. ..$ :'data.frame':	22 obs. of  4 variables:
      .. .. ..$ LastName: chr [1:22] "Kobayashi" "Kuroda" "Fuchida" "Murakami" ...
      .. .. ..$ ForeName: chr [1:22] "Tsutomu" "Junya" "Shin-ichi" "Satoshi" ...
      .. .. ..$ Initials: chr [1:22] "T" "J" "S" "S" ...
      .. .. ..$ order   : int [1:22] 1 2 3 4 5 6 7 8 9 10 ...
      .. ..$ :'data.frame':	15 obs. of  4 variables:
      .. .. ..$ LastName: chr [1:15] "Srivastava" "Rana" "Lacy" "Buadi" ...
      .. .. ..$ ForeName: chr [1:15] "G" "V" "M Q" "F K" ...
      .. .. ..$ Initials: chr [1:15] "G" "V" "MQ" "FK" ...
      .. .. ..$ order   : int [1:15] 1 2 3 4 5 6 7 8 9 10 ...
      .. ..$ :'data.frame':	17 obs. of  4 variables:
      .. .. ..$ LastName: chr [1:17] "Wang" "Fu" "Wu" "Sun" ...
      .. .. ..$ ForeName: chr [1:17] "Juan" "Cheng-cheng" "De-Pei" "Ai-Ning" ...
      .. .. ..$ Initials: chr [1:17] "J" "CC" "DP" "AN" ...
      .. .. ..$ order   : int [1:17] 1 2 3 4 5 6 7 8 9 10 ...
      .. ..$ :'data.frame':	12 obs. of  4 variables:
      .. .. ..$ LastName: chr [1:12] "Valdez" "Wang" "Murray" "Nieto" ...
      .. .. ..$ ForeName: chr [1:12] "Benigno C" "Guiyun" "David" "Yago" ...
      .. .. ..$ Initials: chr [1:12] "BC" "G" "D" "Y" ...
      .. .. ..$ order   : int [1:12] 1 2 3 4 5 6 7 8 9 10 ...
      .. ..$ :'data.frame':	15 obs. of  4 variables:
      .. .. ..$ LastName: chr [1:15] "Gatt" "Takada" "Mani" "Lerner" ...
      .. .. ..$ ForeName: chr [1:15] "Moshe E" "Kohichi" "Mala" "Mikael" ...
      .. .. ..$ Initials: chr [1:15] "ME" "K" "M" "M" ...
      .. .. ..$ order   : int [1:15] 1 2 3 4 5 6 7 8 9 10 ...
      .. ..$ :'data.frame':	2 obs. of  4 variables:
      .. .. ..$ LastName: chr [1:2] "Minnema" "de Keizer"
      .. .. ..$ ForeName: chr [1:2] "Monique C" "Bart"
      .. .. ..$ Initials: chr [1:2] "MC" "B"
      .. .. ..$ order   : int [1:2] 1 2
      .. ..$ :'data.frame':	10 obs. of  4 variables:
      .. .. ..$ LastName: chr [1:10] "Greenberg" "Cousin" "Kumar" "Ketterling" ...
      .. .. ..$ ForeName: chr [1:10] "Alexandra J" "Margot" "Shaji" "Rhett P" ...
      .. .. ..$ Initials: chr [1:10] "AJ" "M" "S" "RP" ...
      .. .. ..$ order   : int [1:10] 1 2 3 4 5 6 7 8 9 10
      .. ..$ :'data.frame':	8 obs. of  4 variables:
      .. .. ..$ LastName: chr [1:8] "Kassambara" "Schoenhals" "Moreaux" "Veyrune" ...
      .. .. ..$ ForeName: chr [1:8] "Alboukadel" "Matthieu" "Jér<U+00F4>me" "Jean-Luc" ...
      .. .. ..$ Initials: chr [1:8] "A" "M" "J" "JL" ...
      .. .. ..$ order   : int [1:8] 1 2 3 4 5 6 7 8
      .. ..$ :'data.frame':	10 obs. of  4 variables:
      .. .. ..$ LastName: chr [1:10] "Tovar" "de Larrea" "Aróstegui" "Cibeira" ...
      .. .. ..$ ForeName: chr [1:10] "Natalia" "Carlos Fernández" "Juan I" "Maria Teresa" ...
      .. .. ..$ Initials: chr [1:10] "N" "CF" "JI" "MT" ...
      .. .. ..$ order   : int [1:10] 1 2 3 4 5 6 7 8 9 10
      .. ..$ :'data.frame':	4 obs. of  4 variables:
      .. .. ..$ LastName: chr [1:4] "Garfall" "Vogl" "Weiss" "Stadtmauer"
      .. .. ..$ ForeName: chr [1:4] "A L" "D T" "B M" "E A"
      .. .. ..$ Initials: chr [1:4] "AL" "DT" "BM" "EA"
      .. .. ..$ order   : int [1:4] 1 2 3 4
      ..@ ISSN                : chr [1:10] "1349-7235" "1476-5551" "0376-2491" "1873-2399" ...
      ..@ Title               : chr [1:10] "Internal medicine (Tokyo, Japan)" "Leukemia" "Zhonghua yi xue za zhi" "Experimental hematology" ...
      ..@ ArticleTitle        : chr [1:10] "The response to second-line induction with bortezomib and dexamethasone is predictive of long-term outcomes pri"| __truncated__ "Long-term outcome with lenalidomide and dexamethasone therapy for newly diagnosed multiple myeloma." "[Retrospective analysis on therapeutic effect of autologous hematopoietic stem cell transplantation in multiple"| __truncated__ "Mechanistic studies on the synergistic cytotoxicity of the nucleoside analogs gemcitabine and clofarabine in mu"| __truncated__ ...
      ..@ ELocationID         : chr [1:10] NA "10.1038/leu.2013.143" NA "10.1016/j.exphem.2013.04.009" ...
      ..@ AbstractText        : chr [1:10] "OBJECTIVE: We retrospectively investigated the efficacy and predictive factors for the treatment outcomes of bo"| __truncated__ "The combination of lenalidomide and dexamethasone (Len-Dex) is a commonly used initial therapy for newly diagno"| __truncated__ "OBJECTIVE: To evaluate the efficacy and prognostic factors of autologous hematopoietic stem cell transplantatio"| __truncated__ "Hematopoietic stem cell transplantation (HSCT) is an established treatment for multiple myeloma (MM), a plasma "| __truncated__ ...
      ..@ Affiliation         : chr [1:10] "Division of Hematology and Oncology, Department of Medicine, Kyoto Prefectural University of Medicine, Japan. t"| __truncated__ "Division of Hematology and Blood and Marrow Transplant, Department of Medicine, Mayo Clinic, Rochester, MN, USA." "Jiangsu Institute of Hematology, First Affiliated Hospital, Soochow University, Key Lab of Thrombosis &amp; Hem"| __truncated__ "Departments of Stem Cell Transplantation and Cellular Therapy, University of Texas MD Anderson Cancer Center, H"| __truncated__ ...
      ..@ Language            : chr [1:10] "eng" "eng" "chi" "eng" ...
      ..@ PublicationType     :List of 10
      .. ..$ : Named chr [1:2] "Journal Article" "Research Support, Non-U.S. Gov't"
      .. .. ..- attr(*, "names")= chr [1:2] "PublicationType" "PublicationType"
      .. ..$ : Named chr [1:3] "Journal Article" "Research Support, N.I.H., Extramural" "Research Support, Non-U.S. Gov't"
      .. .. ..- attr(*, "names")= chr [1:3] "PublicationType" "PublicationType" "PublicationType"
      .. ..$ : Named chr [1:3] "English Abstract" "Journal Article" "Research Support, Non-U.S. Gov't"
      .. .. ..- attr(*, "names")= chr [1:3] "PublicationType" "PublicationType" "PublicationType"
      .. ..$ : Named chr [1:3] "Journal Article" "Research Support, N.I.H., Extramural" "Research Support, Non-U.S. Gov't"
      .. .. ..- attr(*, "names")= chr [1:3] "PublicationType" "PublicationType" "PublicationType"
      .. ..$ : Named chr [1:3] "Journal Article" "Research Support, N.I.H., Extramural" "Research Support, Non-U.S. Gov't"
      .. .. ..- attr(*, "names")= chr [1:3] "PublicationType" "PublicationType" "PublicationType"
      .. ..$ : Named chr [1:2] "Case Reports" "Journal Article"
      .. .. ..- attr(*, "names")= chr [1:2] "PublicationType" "PublicationType"
      .. ..$ : Named chr [1:2] "Journal Article" "Research Support, N.I.H., Extramural"
      .. .. ..- attr(*, "names")= chr [1:2] "PublicationType" "PublicationType"
      .. ..$ : Named chr [1:2] "Journal Article" "Research Support, Non-U.S. Gov't"
      .. .. ..- attr(*, "names")= chr [1:2] "PublicationType" "PublicationType"
      .. ..$ : Named chr [1:2] "Journal Article" "Research Support, Non-U.S. Gov't"
      .. .. ..- attr(*, "names")= chr [1:2] "PublicationType" "PublicationType"
      .. ..$ : Named chr [1:2] "Journal Article" "Review"
      .. .. ..- attr(*, "names")= chr [1:2] "PublicationType" "PublicationType"
      ..@ MedlineTA           : chr [1:10] "Intern Med" "Leukemia" "Zhonghua Yi Xue Za Zhi" "Exp Hematol" ...
      ..@ NlmUniqueID         : chr [1:10] "9204241" "8704895" "7511141" "0402313" ...
      ..@ ISSNLinking         : chr [1:10] "0918-2918" "0887-6924" "0376-2491" "0301-472X" ...
      ..@ PublicationStatus   : chr [1:10] "ppublish" "ppublish" "ppublish" "ppublish" ...
      ..@ ArticleId           : chr [1:10] "DN/JST.JSTAGE/internalmedicine/52.9385" "leu2013143" "23648347" "S0301-472X(13)00201-4" ...
      ..@ Volume              : chr [1:10] "52" "27" "93" "41" ...
      ..@ Issue               : chr [1:10] "9" "10" "2" "8" ...
      ..@ ISOAbbreviation     : chr [1:10] "Intern. Med." "Leukemia" "Zhonghua Yi Xue Za Zhi" "Exp. Hematol." ...
      ..@ MedlinePgn          : chr [1:10] "961-8" "2062-6" "114-8" "719-30" ...
      ..@ CopyrightInformation: chr [1:10] NA NA NA "Published by Elsevier Inc." ...
      ..@ Country             : chr [1:10] "Japan" "United States" "China" "United States" ...
      ..@ GrantID             : chr [1:10] NA "CA 107476" NA "CA 16672" ...
      ..@ Acronym             : chr [1:10] NA "CA" NA "CA" ...
      ..@ Agency              : chr [1:10] NA "NCI NIH HHS" NA "NCI NIH HHS" ...
      ..@ RegistryNumber      : chr [1:10] "0" "4Z8R6ORS6L" NA "0" ...
      ..@ RefSource           : chr [1:10] NA "Lancet Oncol. 2010 Jan;11(1):29-37" NA "J Exp Med. 1995 Nov 1;182(5):1545-56" ...
      ..@ CollectiveName      : chr [1:10] NA NA NA NA ...
      ..@ Mesh                :List of 10
      .. ..$ :'data.frame':	47 obs. of  2 variables:
      .. .. ..$ Heading: Factor w/ 36 levels "administration &amp; dosage",..: 2 4 5 1 3 33 6 1 3 8 ...
      .. .. ..$ Type   : Factor w/ 2 levels "Descriptor","Qualifier": 1 1 1 2 2 2 1 2 2 1 ...
      .. ..$ :'data.frame':	21 obs. of  2 variables:
      .. .. ..$ Heading: Factor w/ 21 levels "administration &amp; dosage",..: 2 3 4 5 21 6 1 9 10 11 ...
      .. .. ..$ Type   : Factor w/ 2 levels "Descriptor","Qualifier": 1 1 1 1 2 1 2 1 1 1 ...
      .. ..$ :'data.frame':	12 obs. of  2 variables:
      .. .. ..$ Heading: Factor w/ 12 levels "diagnosis","Female",..: 2 3 4 5 6 7 1 10 8 9 ...
      .. .. ..$ Type   : Factor w/ 2 levels "Descriptor","Qualifier": 1 1 1 1 1 1 2 2 1 1 ...
      .. ..$ :'data.frame':	27 obs. of  2 variables:
      .. .. ..$ Heading: Factor w/ 25 levels "Adenine Nucleotides",..: 1 2 4 19 24 5 2 6 7 9 ...
      .. .. ..$ Type   : Factor w/ 2 levels "Descriptor","Qualifier": 1 2 1 2 2 1 2 1 1 1 ...
      .. ..$ :'data.frame':	31 obs. of  2 variables:
      .. .. ..$ Heading: Factor w/ 21 levels "antagonists &amp; inhibitors",..: 2 14 4 14 5 14 6 7 14 8 ...
      .. .. ..$ Type   : Factor w/ 2 levels "Descriptor","Qualifier": 1 2 1 2 1 2 1 1 2 1 ...
      .. ..$ :'data.frame':	17 obs. of  2 variables:
      .. .. ..$ Heading: Factor w/ 14 levels "Aged","Biopsy",..: 1 2 3 9 11 12 5 4 6 7 ...
      .. .. ..$ Type   : Factor w/ 2 levels "Descriptor","Qualifier": 1 1 1 2 2 2 1 2 1 1 ...
      .. ..$ :'data.frame':	9 obs. of  2 variables:
      .. .. ..$ Heading: Factor w/ 9 levels "Chromosome Aberrations",..: 1 3 4 6 7 8 2 5 9
      .. .. ..$ Type   : Factor w/ 2 levels "Descriptor","Qualifier": 1 1 1 1 1 1 2 2 1
      .. ..$ :'data.frame':	36 obs. of  2 variables:
      .. .. ..$ Heading: Factor w/ 27 levels "Apoptosis","Bone Marrow Cells",..: 1 12 2 15 20 3 12 4 12 5 ...
      .. .. ..$ Type   : Factor w/ 2 levels "Descriptor","Qualifier": 1 2 1 2 2 1 2 1 2 1 ...
      .. ..$ :'data.frame':	23 obs. of  2 variables:
      .. .. ..$ Heading: Factor w/ 20 levels "Adult","Aged",..: 1 2 4 5 6 20 7 8 9 10 ...
      .. .. ..$ Type   : Factor w/ 2 levels "Descriptor","Qualifier": 1 1 1 1 1 2 1 1 2 1 ...
      .. ..$ :'data.frame':	10 obs. of  2 variables:
      .. .. ..$ Heading: Factor w/ 9 levels "Hematopoietic Stem Cell Transplantation",..: 1 5 2 4 5 6 3 9 7 8
      .. .. ..$ Type   : Factor w/ 2 levels "Descriptor","Qualifier": 1 2 1 1 2 1 2 2 1 1
    


```R
AbstractText(myeloma)
Author(myeloma)
ArticleTitle(myeloma)
Title(myeloma)
PMID(myeloma)
# Use specific functions, you can find each element of the data.
```


<ol class=list-inline>
	<li>'OBJECTIVE: We retrospectively investigated the efficacy and predictive factors for the treatment outcomes of bortezomib plus dexamethasone (BD) as second-line induction therapy prior to high-dose chemotherapy supported by autologous stem cell transplantation (HDT/ASCT) in multiple myeloma (MM) patients.METHODS: Sixty-six transplant eligible MM patients treated by the Kyoto Clinical Hematology Study Group between 2006 and 2011 were investigated. Conventional induction chemotherapy, including vincristine, doxorubicin and dexamethasone (VAD) and high-dose dexamethasone (HDD), was used as first-line induction therapy in all patients, seven (10.6%) of whom attained a very good partial response (VGPR). Of the 59 patients who did not attain VGPR with VAD or HDD, 33 were given BD as second-line induction therapy prior to HDT/ASCT.RESULTS: Patients not treated with BD induction showed an overall response rate (ORR, i.e., better than partial response) of 85.3% after induction therapy, while the ORR of patients treated with BD induction improved from 42.4% after conventional induction therapy to 84.8% after BD. The overall survival (OS) and progression-free survival (PFS) of patients not treated with BD induction were not significantly influenced by the response to induction therapy. Among the patients treated with BD, failure in attaining VGPR prior to ASCT was associated with a significantly shorter PFS and it also tended to show a shorter OS, while the disease stage and achievement of a complete response after HDT/ASCT had no impact on OS or PFS.CONCLUSION: The achievement of at least VGPR with second-line BD induction therapy is a prerequisite for attaining longer OS and PFS after HDT/ASCT.'</li>
	<li>'The combination of lenalidomide and dexamethasone (Len-Dex) is a commonly used initial therapy for newly diagnosed multiple myeloma (MM). Although the initial response rates and toxicity are well known, long-term outcome is not well described. We studied 286 consecutive patients with newly diagnosed MM initially treated with Len-Dex. The median (range) age at diagnosis was 63 (28-92) years, 166 (58%) patients ≤ 65 years and 175 (61%) male. The median estimated duration on Len-Dex was 5.3 months with overall response (≥ partial response) of 72%, including 26% with very good partial response or better. The median overall survival (OS) from the diagnosis was not reached (NR) and the estimated 5-year survival was 71%. The median time to first disease progression, irrespective of transplant status, was 30.2 months. Overall, 143 (50%) patients underwent stem cell transplant. The median OS was NR for patients ≤ 70 years and 5.8 years for the older patients (P=0.01). The 5-year OS estimate for patients in International Staging System stage 1, 2 and 3 were 82, 65, and 44% respectively. There were 21 new second malignancies after MM diagnosis (6.6%). The median survival exceeding 7 years reflects the efficacy of novel agents. The risk of second malignancies doesn\'t appear to be excessive in this population.'</li>
	<li>'OBJECTIVE: To evaluate the efficacy and prognostic factors of autologous hematopoietic stem cell transplantation (ASCT) in multiple myeloma (MM) patients.METHODS: Retrospective analysis was performed in 27 MM patients undergoing ASCT at our hospital from May 2004 to August 2011. After comparing with 28 patients achieving very good partial response (VGPR) or better outcome and not undergoing ASCT, the impact on the extent of response, progression-free survival (PFS) and overall survival (OS) as well as related prognostic factors of MM patients were analyzed.RESULTS: All patients successfully underwent hematopoietic reconstruction without transplantation-related mortality. The complete remission (CR) rate of ASCT group increased from 25.9% (7/27) at pre-ASCT to 70.4% (19/27) at post-ASCT (P &amp;lt; 0.01). The estimated 5-year rate of progression-free survival was 56.2% (median not reached) in the ASCT group and 24.9% (median 29 months) in the non-ASCT group (P &amp;lt; 0.05). The 5-year probability of overall survival was 52.2% (median not reached) in the ASCT group and 33.1% (median 60 months) in the non-ASCT group (P &amp;gt; 0.05). Univariate analysis in ASCT group demonstrated that maintenance/consolidation therapy was associated with PFS (P = 0.010) and OS (P = 0.008).Patients on induction therapy containing bortezomib and early ASCT maintenance therapy all survived without disease progression until final follow-up (P = 0.010).CONCLUSIONS: ASCT can further increase the CR rate, prolong PFS and probably OS. The incorporation of novel agents into induction, consolidation and maintenance phases has optimized the anti-myeloma activity of ASCT and may be important for improved long-term outcomes.'</li>
	<li>'Hematopoietic stem cell transplantation (HSCT) is an established treatment for multiple myeloma (MM), a plasma cell malignancy. To identify an improved pretransplant conditioning regimen, we investigated the cytotoxicity of gemcitabine (Gem) and clofarabine (Clo) combinations toward MM cell lines and patient cell samples. A strong synergism of the two nucleoside analogs, when combined at their approximate IC10 concentrations, was observed. This synergism could be partly due to the observed Gem-mediated phosphorylation and activation of deoxycytidine kinase, resulting in enhanced phosphorylation of Gem and Clo. Their cytotoxicity correlated with a robust activation of the DNA damage response pathway. [Gem+Clo] decreased the mitochondrial membrane potential with a concomitant release of proapoptotic factors into the cytoplasm and nucleus and the activation of apoptosis. Exposure of MM cells to [Gem+Clo] also decreased the level of ribosomal RNA (rRNA), which might have resulted in nucleolar stress, as reported previously, and caused a p53-dependent cell death. A reduction by approximately 50% in the cytotoxicity of Gem and Clo was observed in the presence of pifithrin α, a p53 inhibitor. Furthermore, MM cell lines with mutant p53 exhibited greater resistance to Gem and Clo, supporting a role for the p53 protein in these cytotoxic responses. Our results provide a rationale for clinical trials incorporating [Gem+Clo] combinations as part of conditioning therapy for high-risk patients with MM undergoing HSCT.'</li>
	<li>'Multiple myeloma (MM) is an incurable neoplasm caused by proliferation of malignant plasma cells in the bone marrow (BM). MM is characterized frequently by a complete or partial deletion of chromosome 13q14, seen in more than 50% of patients at diagnosis. Within this deleted region the tripartite motif containing 13 (TRIM13, also termed RFP2) gene product has been proposed to be a tumour suppressor gene (TSG). Here, we show that low expression levels of TRIM13 in MM are associated with chromosome 13q deletion and poor clinical outcome. We present a functional analysis of TRIM13 using a loss-of-function approach, and demonstrate that TRIM13 downregulation decreases tumour cell survival as well as cell cycle progression and proliferation of MM cells. In addition, we provide evidence for the involvement of TRIM13 downregulation in inhibiting the NF kappa B pathway and the activity of the 20S proteasome. Although this data does not support a role of TRIM13 as a TSG, it substantiates important roles of TRIM13 in MM tumour survival and proliferation, underscoring its potential role as a novel target for therapeutic intervention.'</li>
	<li>''</li>
	<li>'We previously reported an increased risk of monoclonal gammopathy of undetermined significance (MGUS) in first-degree relatives of MGUS and multiple myeloma patients. Here, we examine whether primary cytogenetic categories of myeloma differ between patients with and without a family history of MGUS or myeloma. We studied 201 myeloma patients with available data on family history and molecular cytogenetic classification. Myeloma with trisomies was more common in probands who had an affected first-degree relative with MGUS or myeloma compared with those without a family history (46.9% vs. 33.5%, P = 0.125); however, the difference was not statistically significant. Additional studies on the cytogenetic types of myeloma associated with familial tendency are needed.'</li>
	<li>'High throughput DNA microarray has made it possible to outline genes whose expression in malignant plasma cells is associated with short overall survival of patients with Multiple Myeloma (MM). A further step is to elucidate the mechanisms encoded by these genes yielding to drug resistance and/or patients\' short survival. We focus here on the biological role of the DEP (for Disheveled, EGL-10, Pleckstrin) domain contained protein 1A (DEPDC1A), a poorly known protein encoded by DEPDC1A gene, whose high expression in malignant plasma cells is associated with short survival of patients. Using conditional lentiviral vector delivery of DEPDC1A shRNA, we report that DEPDC1A knockdown delayed the growth of human myeloma cell lines (HMCLs), with a block in G2 phase of the cell cycle, p53 phosphorylation and stabilization, and p21(Cip1) accumulation. DEPDC1A knockdown also resulted in increased expression of mature plasma cell markers, including CXCR4, IL6-R and CD38. Thus DEPDC1A could contribute to the plasmablast features of MMCs found in some patients with adverse prognosis, blocking the differentiation of malignant plasma cells and promoting cell cycle.'</li>
	<li>'The emergence of an oligoclonal humoral response, resulting in the appearance of a different serum M-protein to that observed at diagnosis is a well-recognized event after autologous stem cell transplantation in multiple myeloma in complete response, and it has been considered to be a benign phenomenon. The aim of the present study was to investigate the incidence, biological characteristics and prognostic value of the oligoclonal bands in patients with myeloma who underwent autologous transplantation at our institution in the last 18 years. We proceed with a retrospective systematic review of all serum and urine immunofixation studies performed in the 211 patients with multiple myeloma who underwent melphalan-based autologous transplantation. Oligoclonal bands were observed in 34% of the patients, with a significantly higher prevalence with the use of novel agents versus conventional chemotherapy in induction (63% vs. 22%; P=0.0001). The incidence of oligoclonal bands was most frequent in non-IgG isotype, particularly in light chain only myeloma. The oligoclonal phenomenon was almost exclusive to patients in complete remission compared to other degrees of response (87% vs. 13%; P=0.0001), and lasted for a median of 1.35 years, persisting during follow up in all patients except in those who relapsed. In prognostic terms, the presence of oligoclonality resulted in a significantly longer progression-free and overall survival. Patients with oligoclonal humoral response lasting for more than one year after transplantation had a significantly longer clinical progression-free and overall survival than those with shorter duration (P=0.008 and P=0.0001, respectively), likely reflecting the importance of a robust humoral immune response.'</li>
	<li>'Allogeneic hematopoietic cell transplantation for plasma cell myeloma can lead to graft-vs-myeloma immunity and long-term survivorship, but limited efficacy and associated toxicities have prevented its widespread use. Cellular immunotherapies seek to induce more specific, reliable and potent antimyeloma immune responses with less treatment-related risk than is possible with allogeneic transplantation. Strategies under development include infusion of vaccine-primed and ex vivo expanded/costimulated autologous T cells after high-dose melphalan, genetic engineering of autologous T cells with receptors for myeloma-specific epitopes, administration of DC/plasma cell fusions and administration expanded marrow-infiltrating lymphocytes. In addition, novel immunomodulatory drugs such as inhibitors of the programmed death-1 T cell regulatory pathway may synergize with cellular immunotherapies.'</li>
</ol>




<ol>
	<li><table>
<thead><tr><th scope=col>LastName</th><th scope=col>ForeName</th><th scope=col>Initials</th><th scope=col>order</th></tr></thead>
<tbody>
	<tr><td>Kobayashi  </td><td>Tsutomu    </td><td>T          </td><td> 1         </td></tr>
	<tr><td>Kuroda     </td><td>Junya      </td><td>J          </td><td> 2         </td></tr>
	<tr><td>Fuchida    </td><td>Shin-ichi  </td><td>S          </td><td> 3         </td></tr>
	<tr><td>Murakami   </td><td>Satoshi    </td><td>S          </td><td> 4         </td></tr>
	<tr><td>Hatsuse    </td><td>Mayumi     </td><td>M          </td><td> 5         </td></tr>
	<tr><td>Okano      </td><td>Akira      </td><td>A          </td><td> 6         </td></tr>
	<tr><td>Iwai       </td><td>Toshiki    </td><td>T          </td><td> 7         </td></tr>
	<tr><td>Tsutsumi   </td><td>Yasuhiko   </td><td>Y          </td><td> 8         </td></tr>
	<tr><td>Kamitsuji  </td><td>Yuri       </td><td>Y          </td><td> 9         </td></tr>
	<tr><td>Akaogi     </td><td>Teruaki    </td><td>T          </td><td>10         </td></tr>
	<tr><td>Kawata-Iida</td><td>Eri        </td><td>E          </td><td>11         </td></tr>
	<tr><td>Shimizu    </td><td>Daisuke    </td><td>D          </td><td>12         </td></tr>
	<tr><td>Uchiyama   </td><td>Hitoji     </td><td>H          </td><td>13         </td></tr>
	<tr><td>Matsumoto  </td><td>Yosuke     </td><td>Y          </td><td>14         </td></tr>
	<tr><td>Horiike    </td><td>Shigeo     </td><td>S          </td><td>15         </td></tr>
	<tr><td>Nakao      </td><td>Mitsushige </td><td>M          </td><td>16         </td></tr>
	<tr><td>Takahashi  </td><td>Ryoichi    </td><td>R          </td><td>17         </td></tr>
	<tr><td>Kaneko     </td><td>Hiroto     </td><td>H          </td><td>18         </td></tr>
	<tr><td>Uoshima    </td><td>Nobuhiko   </td><td>N          </td><td>19         </td></tr>
	<tr><td>Kobayashi  </td><td>Yutaka     </td><td>Y          </td><td>20         </td></tr>
	<tr><td>Shimazaki  </td><td>Chihiro    </td><td>C          </td><td>21         </td></tr>
	<tr><td>Taniwaki   </td><td>Masafumi   </td><td>M          </td><td>22         </td></tr>
</tbody>
</table>
</li>
	<li><table>
<thead><tr><th scope=col>LastName</th><th scope=col>ForeName</th><th scope=col>Initials</th><th scope=col>order</th></tr></thead>
<tbody>
	<tr><td>Srivastava </td><td>G          </td><td>G          </td><td> 1         </td></tr>
	<tr><td>Rana       </td><td>V          </td><td>V          </td><td> 2         </td></tr>
	<tr><td>Lacy       </td><td>M Q        </td><td>MQ         </td><td> 3         </td></tr>
	<tr><td>Buadi      </td><td>F K        </td><td>FK         </td><td> 4         </td></tr>
	<tr><td>Hayman     </td><td>S R        </td><td>SR         </td><td> 5         </td></tr>
	<tr><td>Dispenzieri</td><td>A          </td><td>A          </td><td> 6         </td></tr>
	<tr><td>Gertz      </td><td>M A        </td><td>MA         </td><td> 7         </td></tr>
	<tr><td>Dingli     </td><td>D          </td><td>D          </td><td> 8         </td></tr>
	<tr><td>Zeldenrust </td><td>S          </td><td>S          </td><td> 9         </td></tr>
	<tr><td>Russell    </td><td>S          </td><td>S          </td><td>10         </td></tr>
	<tr><td>McCurdy    </td><td>A          </td><td>A          </td><td>11         </td></tr>
	<tr><td>Kapoor     </td><td>P          </td><td>P          </td><td>12         </td></tr>
	<tr><td>Kyle       </td><td>R          </td><td>R          </td><td>13         </td></tr>
	<tr><td>Rajkumar   </td><td>S V        </td><td>SV         </td><td>14         </td></tr>
	<tr><td>Kumar      </td><td>S          </td><td>S          </td><td>15         </td></tr>
</tbody>
</table>
</li>
	<li><table>
<thead><tr><th scope=col>LastName</th><th scope=col>ForeName</th><th scope=col>Initials</th><th scope=col>order</th></tr></thead>
<tbody>
	<tr><td>Wang       </td><td>Juan       </td><td>J          </td><td> 1         </td></tr>
	<tr><td>Fu         </td><td>Cheng-cheng</td><td>CC         </td><td> 2         </td></tr>
	<tr><td>Wu         </td><td>De-Pei     </td><td>DP         </td><td> 3         </td></tr>
	<tr><td>Sun        </td><td>Ai-Ning    </td><td>AN         </td><td> 4         </td></tr>
	<tr><td>Xue        </td><td>Sheng-li   </td><td>SL         </td><td> 5         </td></tr>
	<tr><td>Xin        </td><td>Xue        </td><td>X          </td><td> 6         </td></tr>
	<tr><td>Hu         </td><td>Xiao-hui   </td><td>XH         </td><td> 7         </td></tr>
	<tr><td>Wang       </td><td>Ying       </td><td>Y          </td><td> 8         </td></tr>
	<tr><td>Qiu        </td><td>Hui-Ying   </td><td>HY         </td><td> 9         </td></tr>
	<tr><td>Jin        </td><td>Zheng-ming </td><td>ZM         </td><td>10         </td></tr>
	<tr><td>Miao       </td><td>Miao       </td><td>M          </td><td>11         </td></tr>
	<tr><td>Tang       </td><td>Xiao-wen   </td><td>XW         </td><td>12         </td></tr>
	<tr><td>Han        </td><td>Yue        </td><td>Y          </td><td>13         </td></tr>
	<tr><td>Ma         </td><td>Xiao       </td><td>X          </td><td>14         </td></tr>
	<tr><td>He         </td><td>Guang-sheng</td><td>GS         </td><td>15         </td></tr>
	<tr><td>Chang      </td><td>Wei-rong   </td><td>WR         </td><td>16         </td></tr>
	<tr><td>Chen       </td><td>Su-ning    </td><td>SN         </td><td>17         </td></tr>
</tbody>
</table>
</li>
	<li><table>
<thead><tr><th scope=col>LastName</th><th scope=col>ForeName</th><th scope=col>Initials</th><th scope=col>order</th></tr></thead>
<tbody>
	<tr><td>Valdez    </td><td>Benigno C </td><td>BC        </td><td> 1        </td></tr>
	<tr><td>Wang      </td><td>Guiyun    </td><td>G         </td><td> 2        </td></tr>
	<tr><td>Murray    </td><td>David     </td><td>D         </td><td> 3        </td></tr>
	<tr><td>Nieto     </td><td>Yago      </td><td>Y         </td><td> 4        </td></tr>
	<tr><td>Li        </td><td>Yang      </td><td>Y         </td><td> 5        </td></tr>
	<tr><td>Shah      </td><td>Jatin     </td><td>J         </td><td> 6        </td></tr>
	<tr><td>Turturro  </td><td>Francesco </td><td>F         </td><td> 7        </td></tr>
	<tr><td>Wang      </td><td>Michael   </td><td>M         </td><td> 8        </td></tr>
	<tr><td>Weber     </td><td>Donna M   </td><td>DM        </td><td> 9        </td></tr>
	<tr><td>Champlin  </td><td>Richard E </td><td>RE        </td><td>10        </td></tr>
	<tr><td>Qazilbash </td><td>Muzaffar H</td><td>MH        </td><td>11        </td></tr>
	<tr><td>Andersson </td><td>Borje S   </td><td>BS        </td><td>12        </td></tr>
</tbody>
</table>
</li>
	<li><table>
<thead><tr><th scope=col>LastName</th><th scope=col>ForeName</th><th scope=col>Initials</th><th scope=col>order</th></tr></thead>
<tbody>
	<tr><td>Gatt       </td><td>Moshe E    </td><td>ME         </td><td> 1         </td></tr>
	<tr><td>Takada     </td><td>Kohichi    </td><td>K          </td><td> 2         </td></tr>
	<tr><td>Mani       </td><td>Mala       </td><td>M          </td><td> 3         </td></tr>
	<tr><td>Lerner     </td><td>Mikael     </td><td>M          </td><td> 4         </td></tr>
	<tr><td>Pick       </td><td>Marjorie   </td><td>M          </td><td> 5         </td></tr>
	<tr><td>Hideshima  </td><td>Teru       </td><td>T          </td><td> 6         </td></tr>
	<tr><td>Carrasco   </td><td>Daniel E   </td><td>DE         </td><td> 7         </td></tr>
	<tr><td>Protopopov </td><td>Alexei     </td><td>A          </td><td> 8         </td></tr>
	<tr><td>Ivanova    </td><td>Elena      </td><td>E          </td><td> 9         </td></tr>
	<tr><td>Sangfelt   </td><td>Olle       </td><td>O          </td><td>10         </td></tr>
	<tr><td>Grandér    </td><td>Dan        </td><td>D          </td><td>11         </td></tr>
	<tr><td>Barlogie   </td><td>Bart       </td><td>B          </td><td>12         </td></tr>
	<tr><td>Shaughnessy</td><td>John D     </td><td>JD         </td><td>13         </td></tr>
	<tr><td>Anderson   </td><td>Kenneth C  </td><td>KC         </td><td>14         </td></tr>
	<tr><td>Carrasco   </td><td>Daniel R   </td><td>DR         </td><td>15         </td></tr>
</tbody>
</table>
</li>
	<li><table>
<thead><tr><th scope=col>LastName</th><th scope=col>ForeName</th><th scope=col>Initials</th><th scope=col>order</th></tr></thead>
<tbody>
	<tr><td>Minnema  </td><td>Monique C</td><td>MC       </td><td>1        </td></tr>
	<tr><td>de Keizer</td><td>Bart     </td><td>B        </td><td>2        </td></tr>
</tbody>
</table>
</li>
	<li><table>
<thead><tr><th scope=col>LastName</th><th scope=col>ForeName</th><th scope=col>Initials</th><th scope=col>order</th></tr></thead>
<tbody>
	<tr><td>Greenberg  </td><td>Alexandra J</td><td>AJ         </td><td> 1         </td></tr>
	<tr><td>Cousin     </td><td>Margot     </td><td>M          </td><td> 2         </td></tr>
	<tr><td>Kumar      </td><td>Shaji      </td><td>S          </td><td> 3         </td></tr>
	<tr><td>Ketterling </td><td>Rhett P    </td><td>RP         </td><td> 4         </td></tr>
	<tr><td>Knudson    </td><td>Ryan A     </td><td>RA         </td><td> 5         </td></tr>
	<tr><td>Larson     </td><td>Dirk       </td><td>D          </td><td> 6         </td></tr>
	<tr><td>Colby      </td><td>Colin      </td><td>C          </td><td> 7         </td></tr>
	<tr><td>Scott      </td><td>Christopher</td><td>C          </td><td> 8         </td></tr>
	<tr><td>Vachon     </td><td>Celine M   </td><td>CM         </td><td> 9         </td></tr>
	<tr><td>Rajkumar   </td><td>S Vincent  </td><td>SV         </td><td>10         </td></tr>
</tbody>
</table>
</li>
	<li><table>
<thead><tr><th scope=col>LastName</th><th scope=col>ForeName</th><th scope=col>Initials</th><th scope=col>order</th></tr></thead>
<tbody>
	<tr><td>Kassambara   </td><td>Alboukadel   </td><td>A            </td><td>1            </td></tr>
	<tr><td>Schoenhals   </td><td>Matthieu     </td><td>M            </td><td>2            </td></tr>
	<tr><td><span style=white-space:pre-wrap>Moreaux    </span></td><td>Jér&lt;U+00F4&gt;me                                </td><td>J                                                  </td><td>3                                                  </td></tr>
	<tr><td>Veyrune      </td><td>Jean-Luc     </td><td>JL           </td><td>4            </td></tr>
	<tr><td>Rème         </td><td>Thierry      </td><td>T            </td><td>5            </td></tr>
	<tr><td>Goldschmidt  </td><td>Hartmut      </td><td>H            </td><td>6            </td></tr>
	<tr><td>Hose         </td><td>Dirk         </td><td>D            </td><td>7            </td></tr>
	<tr><td>Klein        </td><td>Bernard      </td><td>B            </td><td>8            </td></tr>
</tbody>
</table>
</li>
	<li><table>
<thead><tr><th scope=col>LastName</th><th scope=col>ForeName</th><th scope=col>Initials</th><th scope=col>order</th></tr></thead>
<tbody>
	<tr><td>Tovar           </td><td>Natalia         </td><td>N               </td><td> 1              </td></tr>
	<tr><td>de Larrea       </td><td>Carlos Fernández</td><td>CF              </td><td> 2              </td></tr>
	<tr><td>Aróstegui       </td><td>Juan I          </td><td>JI              </td><td> 3              </td></tr>
	<tr><td>Cibeira         </td><td>Maria Teresa    </td><td>MT              </td><td> 4              </td></tr>
	<tr><td>Rosi&lt;U+00F1&gt;ol                                    </td><td><span style=white-space:pre-wrap>Laura           </span></td><td>L                                                       </td><td> 5                                                      </td></tr>
	<tr><td>Rovira          </td><td>Montserrat      </td><td>M               </td><td> 6              </td></tr>
	<tr><td>Elena           </td><td>Montserrat      </td><td>M               </td><td> 7              </td></tr>
	<tr><td>Filella         </td><td>Xavier          </td><td>X               </td><td> 8              </td></tr>
	<tr><td>Yagüe           </td><td>Jordi           </td><td>J               </td><td> 9              </td></tr>
	<tr><td>Bladé           </td><td>Joan            </td><td>J               </td><td>10              </td></tr>
</tbody>
</table>
</li>
	<li><table>
<thead><tr><th scope=col>LastName</th><th scope=col>ForeName</th><th scope=col>Initials</th><th scope=col>order</th></tr></thead>
<tbody>
	<tr><td>Garfall   </td><td>A L       </td><td>AL        </td><td>1         </td></tr>
	<tr><td>Vogl      </td><td>D T       </td><td>DT        </td><td>2         </td></tr>
	<tr><td>Weiss     </td><td>B M       </td><td>BM        </td><td>3         </td></tr>
	<tr><td>Stadtmauer</td><td>E A       </td><td>EA        </td><td>4         </td></tr>
</tbody>
</table>
</li>
</ol>




<ol class=list-inline>
	<li>'The response to second-line induction with bortezomib and dexamethasone is predictive of long-term outcomes prior to high-dose chemotherapy with autologous stem cell transplantation for multiple myeloma.'</li>
	<li>'Long-term outcome with lenalidomide and dexamethasone therapy for newly diagnosed multiple myeloma.'</li>
	<li>'[Retrospective analysis on therapeutic effect of autologous hematopoietic stem cell transplantation in multiple myeloma patients].'</li>
	<li>'Mechanistic studies on the synergistic cytotoxicity of the nucleoside analogs gemcitabine and clofarabine in multiple myeloma: relevance of p53 and its clinical implications.'</li>
	<li>'TRIM13 (RFP2) downregulation decreases tumour cell growth in multiple myeloma through inhibition of NF Kappa B pathway and proteasome activity.'</li>
	<li>'False-positive PET scan after bone marrow biopsy.'</li>
	<li>'Differences in the distribution of cytogenetic subtypes between multiple myeloma patients with and without a family history of monoclonal gammopathy and multiple myeloma.'</li>
	<li>'Inhibition of DEPDC1A, a bad prognostic marker in multiple myeloma, delays growth and induces mature plasma cell markers in malignant plasma cells.'</li>
	<li>'Natural history and prognostic impact of oligoclonal humoral response in patients with multiple myeloma after autologous stem cell transplantation: long-term results from a single institution.'</li>
	<li>'Cellular immunotherapy for plasma cell myeloma.'</li>
</ol>




<ol class=list-inline>
	<li>'Internal medicine (Tokyo, Japan)'</li>
	<li>'Leukemia'</li>
	<li>'Zhonghua yi xue za zhi'</li>
	<li>'Experimental hematology'</li>
	<li>'British journal of haematology'</li>
	<li>'British journal of haematology'</li>
	<li>'European journal of haematology'</li>
	<li>'PloS one'</li>
	<li>'Haematologica'</li>
	<li>'Bone marrow transplantation'</li>
</ol>




<ol class=list-inline>
	<li>'23648714'</li>
	<li>'23648667'</li>
	<li>'23648347'</li>
	<li>'23648290'</li>
	<li>'23647456'</li>
	<li>'23647318'</li>
	<li>'23647020'</li>
	<li>'23646139'</li>
	<li>'23645688'</li>
	<li>'23645169'</li>
</ol>




```R
install.packages("EUtilsSummary")
# Using the R3.4.2 to run the following commands.
```

    Warning message:
    "package 'EUtilsSummary' is not available (for R version 3.4.2)"

> library(EUtilsSummary)<br>
####### be sure that the 'EUtilsSummary' package has been installed. 
> cancer <- EUtilsSummary("cancer[ti]", type="research", db="pubmed")
> class(cancer)
> str(cancer)
> cancer@id[1:10]
> cancer.ris <- EUtilsGet(cancer, type="efetch", db="pubmed")
> class(cancer.ris)
