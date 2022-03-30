import pandas as pd
import numpy as np
import radiomics
from radiomics import featureextractor
settings = {}
settings['binWidth'] = 25
settings['resampledPixelSpacing'] =[1,1,1]
extractor=featureextractor.RadiomicsFeatureExtractor(**settings)
extractor.enableAllImageTypes()
#extractor.enableImageTypeByName('Original',enabled=True, customArgs=None)
dataA=pd.DataFrame()
for i in range(1,6):
    image=str(i)+'.nrrd'
    label=str(i)+'l.nrrd'
    feature_1=extractor.execute(image,label)
    featureA=pd.DataFrame([feature_1])
    dataA=pd.concat([dataA,featureA])
dataA.to_excel("dataA.xlsx")
