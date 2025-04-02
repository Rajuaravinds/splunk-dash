 spath input=symcSEDRData
| spath input=symcSEDRData path=device_domain
| spath input=symcSEDRData path=edr_enriched_data.category_name
| spath input=symcSEDRData path=edr_enriched_data.rule_name
| spath input=symcSEDRData path=edr_enriched_data.suspicion_score
| spath input=symcSEDRData path=logging_device_name
| spath input=symcSEDRData path=attacks{}.technique_uid
| spath input=symcSEDRData path=attacks{}.technique_name
| spath input=symcSEDRData path=logging_device_ip
| spath input=symcSEDRData path=device_time
| spath input=symcSEDRData path=path
| spath input=symcSEDRData path=cmd_line
| spath input=symcSEDRData path=pid
| table device_domain category_name rule_name suspicion_score logging_device_name technique_uid technique_name logging_device_ip device_time path cmd_line pid
