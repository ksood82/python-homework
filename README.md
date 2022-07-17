# python-homework

import statistics 
import numpy as np

df = pd.read_csv("../PyBank/budget_data.csv")


Total=len(df)
PL = df['Profit/Losses'].sum()

PLList = list(df['Profit/Losses'])
dateProfitLossesList = df['Date']

changeList = []

for i in range(len(df)-1):
    a = PLList[i]
    b = PLList[i+1]
    changeList.append(b-a)
    minChange = min(changeList)
    maxChange = max(changeList)  
    avgChance = round(np.mean(changeList),2)

print(f"Financial Analysis")
print(f"----------------------------------")
print(f"Total Months {Total}")
print(f"Your profit is: ${PL}")
print(f"Average  Change: ${avgChance}")
print(f"Greatest Increase in Profits: (${maxChange})")
print(f"Greatest Decrease in Profits: (${minChange})")


Financial Analysis
----------------------------------
Total Months 86
Your profit is: $38382578
Average  Change: $-2315.12
Greatest Increase in Profits: ($1926159)
Greatest Decrease in Profits: ($-2196167)
