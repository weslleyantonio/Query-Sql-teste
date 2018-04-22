SELECT title, 
COUNT(CASE WHEN applications.score > 25 THEN 1 END) as Over25,
COUNT(CASE WHEN applications.score > 50 THEN 1 END) as Over50,
COUNT(CASE WHEN applications.score > 75 THEN 1 END) as Over75
FROM applications inner join jobs on applications.job_id = jobs.id
GROUP BY title;