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

## Example
![need_to_update](https://cloud.githubusercontent.com/assets/12140221/20521041/43008dae-b0a1-11e6-9f0e-e400ca404a10.PNG)



