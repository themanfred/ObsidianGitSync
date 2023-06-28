EX:
## Feature columns describe how to use the input.

my_feature_columns = []

for key in train.keys():

    my_feature_columns.append(tf.feature_column.numeric_column(key=key))

print(my_feature_columns)



learning