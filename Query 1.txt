SELECT name, COUNT(job_id) 
FROM candidates LEFT JOIN applications
ON candidates.id = applications.candidate_id
GROUP BY name
HAVING COUNT(job_id) < 3
ORDER BY COUNT(job_id) DESC;

