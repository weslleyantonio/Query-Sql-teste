SELECT name, title,  score
FROM candidates INNER JOIN applications
ON candidates.id = applications.candidate_id 
INNER JOIN jobs ON jobs.id = applications.job_id
WHERE score = (SELECT MAX(score)
                            FROM applications
                            WHERE candidates.id = applications.candidate_id )
GROUP BY name, title, score
ORDER BY name;