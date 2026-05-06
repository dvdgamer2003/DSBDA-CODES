https://chatgpt.com/share/69fa4deb-b504-83a7-9e1b-ed322a969352    explanation link 1
theory link  https://chatgpt.com/share/69fa4e31-32d8-8322-b32e-1d7a92e5cda9



Q1 = df['Marks'].quantile(0.25)
Q3 = df['Marks'].quantile(0.75)

IQR = Q3 - Q1

lower = Q1 - 1.5 * IQR
upper = Q3 + 1.5 * IQR

outliers = df[(df['Marks'] < lower) | (df['Marks'] > upper)]

print(outliers)


TN, FP, FN, TP = cm.ravel()

accuracy = (TP + TN) / (TP + TN + FP + FN)
error_rate = (FP + FN) / (TP + TN + FP + FN)
precision = TP / (TP + FP)
recall = TP / (TP + FN)

print("Accuracy:", accuracy)
print("Error Rate:", error_rate)
print("Precision:", precision)
print("Recall:", recall)
