__The Pipeline Structure__:
  1. Document Reset PR
  2. ANNIE English Tokeniser
  3. ANNIE Sentence Splitter
  4. ANNIE POS Tagger
  5. ANNIE Gazetteer
  6. BWP Gazetteer : {annotationSetName:, avoidOverlapingAnnotation: true, caseSensitive:false, normalizeDistanceThreshold:0.15, wholeWordsOnly:true}
  7. Annotation Set Transfer: {___annotationTypes:[html,span,p,page,body], copyAnnotations:true, inputASName: Original markups, outputASName:, tagASName: Original markups, textTagName:, transferAllUnlessFound: true___} 
  8. Case Insensitive Gazetteer: {___caseSensitive: false, encoding: UTF-8, gazetteerFeatureSeparator: ":", listURL:~path/gazet.def___}
  9. Case Sensitive Gazetteer: {___caseSensitive: true, encoding: UTF-8, gazetteerFeatureSeparator: ":", listURL:~path/gazetCaseSensitive.def___}
  10. Main JAPE
  11. Clean JAPE

_Logic Flow_
The approach of this entity recognition is All markers are stored in BWP Gazetteer, and they are case insensitive 
Then, using the annotation set transfer to send the original markups as input.
Case Insensitive gazetteer mostly contains name of location from ___subdistrict__: kelurahan.lst_, ___district__: kecamatan.lst_, ___city__: city.lst_, also  ___state__: province.lst_.
and case sensitive gazetteer to keep the lookup for patient name (__title_CaseSensitive.lst__) and hospital name (__hospital_CaseSensitive__)

__The details explanation of the function is already included in the each JAPE file__

__Please use the html file provided in the new_new_medical_invoice to test the logic__

__This works best on :__
1. RS TELOGOREJO 1: 6 Datapoints (Address_Patient, Date_In, Date_Out, Doctor_Name, HospitalName, PatientName,)
2. RS TELOGOREJO 3: 4 Datapoints (Date_In, Date_Out, Doctor_Name, HospitalName)
3. RSIA CATHERINE BOOTH: 4 Datapoints (Date_In, Date_Out, Doctor_Name, HospitalName)
4. RS PREMIER SURABAYA: 3 Datapoints (Date_In, Date_Out, HospitalName)
5. RS PANTAI INDAH KAPUK: 3 Datapoints (Date_In, Date_Out, HospitalName)
6. COLUMBIA ASIA 3: 3 Datapoints (Date_Out,Doctor_Name, HospitalName)
7. COLUMBIA ASIA 1: 2 Datapoints (Date_Out, HospitalName)

