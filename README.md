__The Pipeline Structure__:
  1. Document Reset PR
  2. ANNIE English Tokeniser
  3. ANNIE Sentence Splitter
  4. ANNIE POS Tagger
  5. ANNIE Gazetteer
  6. BWP Gazetteer : {annotationSetName:, avoidOverlapingAnnotation: true, caseSensitive:false, normalizeDistanceThreshold:0.15, wholeWordsOnly:true}
  7. Annotation Set Transfer: {annotationTypes:[html,span,p,page,body], copyAnnotations:true, inputASName: Original markups, outputASName:, tagASName: Original markups, textTagName:, transferAllUnlessFound: true} 
  8. Case Insensitive Gazetteer: {caseSensitive: false, encoding: UTF-8, gazetteerFeatureSeparator: ":", listURL:~path/gazet.def}
  9. Case Sensitive Gazetteer: {caseSensitive: true, encoding: UTF-8, gazetteerFeatureSeparator: ":", listURL:~path/gazetCaseSensitive.def}
  10. Main JAPE
  11. Clean JAPE

_Logic Flow_
The approach of this entity recognition is All markers are stored in BWP Gazetteer, and they are case insensitive 
Then, using the annotation set transfer to send the original markups as input.
Case Insensitive gazetteer mostly contains name of location from ___subdistrict__: kelurahan.lst_, ___district__: kecamatan.lst_,___city__: city.lst_, also  ___state__: province.lst_.
and case sensitive gazetteer to keep the lookup for patient name (__title_CaseSensitive.lst__) and hospital name (__hospital_CaseSensitive__)
