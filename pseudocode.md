# NetViz Pseudocode

## ingest_logs(file)
- open the file
- read each line into a structured format  
- return a list of log entries  

## apply_heuristics(log_entries)
- suspicious = []  
- for each entry in log_entries:  
  - if entry.port is uncommon → flag "rare port"  
  - if entry.process in unusual location → flag "weird directory"  
  - if entry.ip has burst connections → flag "suspicious burst connection"  
- return suspicious  

## build_graph(log_entries, suspicious_flags)
- create graph nodes for processes, IPs, ports  
- draw edges for connections  
- highlight suspicious nodes/edges  
- return graph object  

## export_report(suspicious_flags)
- create pdf/html file  
- list suspicious entries + reasons  
- save to disk  
