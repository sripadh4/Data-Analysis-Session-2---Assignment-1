# Data-Analysis-Session-2---Assignment-1

Count the difference in an array back to every zero or the start of the series, whichever is closer

import pandas as pd
import numpy as np
df = pd.DataFrame({'X': [7, 2, 0, 3, 4, 2, 5, 0, 3, 4]})
df['Y'] = pd.Series(np.where(df['X']==0, 0 , 1))
a = df['Y'].isin([1])
df.assign(Y=a.groupby((a.diff() == 1).cumsum()).cumsum())
