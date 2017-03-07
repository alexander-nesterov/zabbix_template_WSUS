# Zabbix template (WSUS)

```sql
SELECT count(tbComputerTarget.FullDomainName) AS [Count]
FROM tbUpdateStatusPerComputer INNER JOIN tbComputerTarget ON tbUpdateStatusPerComputer.TargetID = tbComputerTarget.TargetID
WHERE (NOT (tbUpdateStatusPerComputer.SummarizationState IN ('1', '4')))
AND tbComputerTarget.FullDomainName = '{HOST.NAME}'
```
### SummarizationState:
- 1 = Not Installed
- 2 = Needed
- 3 = Downloaded
- 4 = Installed
- 5 = Failed

### Item
![items](https://cloud.githubusercontent.com/assets/12140221/23650097/88e69156-0353-11e7-9008-54cc7dab932c.PNG)


## Example
![need_to_update](https://cloud.githubusercontent.com/assets/12140221/20521041/43008dae-b0a1-11e6-9f0e-e400ca404a10.PNG)



