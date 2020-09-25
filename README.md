# ZeroLogonAssess
Patch and enforcement key assessment for CVE 2020-1472

Script will:
- Detect all Domain Controllers
- Scan for relevant installed updated
- Check for enforcement registry keys

This is loosely based on (CISA Validation script)[https://github.com/cisagov/cyber.dhs.gov/tree/master/assets/report/ed-20-04_script]. Unfortunately whilst attempting to (fix bugged output)[https://github.com/cisagov/cyber.dhs.gov/issues/163] I came to the view that the existing code's workflow of appending to a csv file and reading it back just needed to be rewritten.

In the process I added a scan for the enforcement key.

Note the nature of cumulative updates means the list of patches will soon be out of date.

# Use

```
PS C:\Users\administrator\Downloads> .\ZeroLogonAccess.ps1
Zerologon validation of domain at 09/25/2020 13:14:11
Evaluating Domain Controller: dc1.ad.domain.com
Evaluating Domain Controller: dc2.ad.domain.com

DomainController             OperatingSystem                          Update    Compliance Enforcement
----------------             ---------------                          ------    ---------- ----------
dc1.ad.domain.com            Microsoft Windows Server 2016 Datacenter KB4571694       True        True
dc2.ad.domain.com            Microsoft Windows Server 2016 Datacenter KB4571694       True        True
```
