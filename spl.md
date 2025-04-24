| tstats summariesonly=true allow_old_summaries=true count 
    from datamodel=Threat_Intelligence.Threat_Activity 
    by _time, Threat_Activity.threat_match_field, 
    Threat_Activity.threat_match_value, Threat_Activity.threat_collection, 
    Threat_Activity.threat_key, Threat_Activity.threat_collection_key, 
    Threat_Activity.src, Threat_Activity.dest, 
    orig_sourcetype 
    span=1d 
| convert timeformat="%Y-%m-%d %H:%M:%S" ctime(_time)
| stats count as threat_match by _time, threat_collection, threat_match_field, threat_key, dest, src, orig_sourcetype
| timechart span=1d sum(threat_match) as daily_threat_match
| eventstats avg(daily_threat_match) as avg_threat_match
| where daily_threat_match > avg_threat_match
