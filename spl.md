<your_search_query>
| spath input=data path=process.uid output=process_uid
| spath input=data path=process.file.signature_level_id output=process_file_signature_level_id
| spath input=data path=process.file.path output=process_file_path
| spath input=data path=process.file.signature_value_ids output=process_file_signature_value_ids
| spath input=data path=process.file.sha2 output=process_file_sha2
| spath input=data path=process.file.normalized_path output=process_file_normalized_path
| spath input=data path=process.file.original_name output=process_file_original_name
| spath input=data path=process.file.name output=process_file_name
| spath input=data path=process.cmd_line output=process_cmd_line
| spath input=data path=process.pid output=process_pid
| spath input=data path=process.user.name output=process_user_name
| spath input=data path=process.user.sid output=process_user_sid
| spath input=data path=edr_enriched_data.rule_name output=edr_enriched_data_rule_name
| spath input=data path=edr_enriched_data.suspicion_score output=edr_enriched_data_suspicion_score
| spath input=data path=edr_enriched_data.rule_description output=edr_enriched_data_rule_description
| spath input=data path=attacks{} technique_name output=attacks_technique_name
| spath input=data path=attacks{}.technique_uid output=attacks_technique_uid
| spath input=data path=logging_device_name output=logging_device_name
| spath input=data path=user_domain output=user_domain
| spath input=data path=logging_device_ip output=logging_device_ip
