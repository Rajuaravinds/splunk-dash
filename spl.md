 eval normalized_last_time = strptime(last_time, "%Y-%m-%dT%H:%M:%S")
| eval normalized_end_date = strptime(replace(end_date, "\+00:00", ""), "%Y-%m-%d %H:%M:%S")
| eval action_after_end = if(normalized_last_time > normalized_end_date, "Yes", "No"
