# Date Time String Generation in Different Languages

| Document Information
| --------------------
| Author: Todd Fiedler
| Revised: 4/4/2022

## Description

Some examples of format strings or commands for generating ISO 8601 date time strings that are good for log files. 

## Examples
### PowerShell

#### with microseconds:

```csharp
[datetime]::now.ToUniversalTime().tostring("yyyy-MM-ddTHH:mm:ss.fffK")
```

#### without microseconds:

```csharp
[datetime]::now.ToUniversalTime().tostring("yyyy-MM-ddTHH:mm:ssK")
```

### Python

#### with microseconds:

```python
datetime.datetime.utcnow().isoformat("T")+"Z"
```
or
```python
datetime.datetime.utcnow().strftime("%Y-%m-%dT%H:%M:%S.%fZ")
```

#### without microseconds:

```python
datetime.datetime.utcnow().strftime("%Y-%m-%dT%H:%M:%SZ")
```
or
```python
datetime.datetime.utcnow().replace(microsecond=0).isoformat("T")+"Z"
```
