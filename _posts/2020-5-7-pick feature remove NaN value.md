let say we have a 200 columns? how do we eliminate the less important columns?
One we can count the NaN in that row. For example, if the rows is 1 million, and there are 900,000 NaN 
in that row then 90% of the value is missing in that columns.
'''
#count the amount of information each column has
colCount = train_numeric.count()
Column_ListHasOverSeventyInformation=[]
Column_ListOfunderthirtyInformatiion=[]
#Grab all columns that has more than 70 precent information
for index, value in colCount.iteritems():
    if value / 1183747 >= .70:
        Column_ListHasOverSeventyInformation.append(index)
    #else:
        #Column_ListOfunderthirtyInformatiion.append(index)
'''

Then we can feature important those column and rank the reminder.
'''
#plt.hist(clf.feature_importances_[clf.feature_importances_>0])
important_indices = np.where(clf.feature_importances_>0.005)[0]
print(important_indices)

# load entire dataset for these features. 
# note where the feature indices are split so we can load the correct ones straight from read_csv
n_date_features = 1156
X = np.concatenate([
    pd.read_csv("F:\\Pycharm\\SCDS-borchFactory\\data\\train_date.csv", index_col=0, dtype=np.float32,
                usecols=np.concatenate([[0], important_indices[important_indices < n_date_features] + 1])).values,
    pd.read_csv("F:\\Pycharm\\SCDS-borchFactory\\data\\train_numeric.csv", index_col=0, dtype=np.float32,
                usecols=np.concatenate([[0], important_indices[important_indices >= n_date_features] + 1 - 1156])).values
], axis=1)
y = pd.read_csv("F:\\Pycharm\\SCDS-borchFactory\\data\\train_numeric.csv", index_col=0, dtype=np.float32, usecols=[0,969]).values.ravel()

'''