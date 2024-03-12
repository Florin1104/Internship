1. docker run --name MySqlFlorin -p 3306:3306 -e MYSQL_ROOT_PASSWORD=Aa1234_b -d mysql
2. docker exec -it MySqlFlorin mysql -uroot -p
3. CREATE DATABASE company;
--descarcat "company.sql"
4. docker cp C:\Users\Dell\Downloads\company.sql MySqlFlorin:/var/lib/mysql/company/company.sql
5. USE company;
6. SOURCE /var/lib/mysql/company/company.sql; 

( ERROR 1366 (HY000): Incorrect integer value: 'Consulting' for column 'department' at row 41)
('Hannah', 'Murphy', 7, 'Consulting', 86000.00)



7. CREATE USER 'florin'@'%' IDENTIFIED BY 'florin1234';
8. GRANT ALL PRIVILEGES ON company.* TO 'florin'@'%';
9. FLUSH PRIVILEGES;
10. docker exec -it MySqlFlorin mysql -uflorin -p

Am interogat tabelele departments si employees -> in employees nu s-au importat datele din cauza erori primite la comanda numarul 5
Am editat fisierul .sql, am corectat linia respectiva si am introdus id-u cu numarul 7, id corespunzator valori "Consulting".

Am rulat inca odata comanda numarul 4, 5, 6.


Am corectat valorile din tabele "departments" si "positions".
11. select * from departments where department_id > 8; 
12. delete from departments where department_id > 8;
13. select * from positions where position_id > 11;
14. delete from positions where position_id > 11;


15. 
SELECT
    d.department_id,
    d.department_name,
    AVG(e.salary) AS average_salary
FROM
    departments d
LEFT JOIN
    employees e ON d.department_id = e.department
GROUP BY
    d.department_id, d.department_name;


result:
+---------------+-----------------+----------------+
| department_id | department_name | average_salary |
+---------------+-----------------+----------------+
|             1 | Sales           |   60000.000000 |
|             2 | Engineering     |   75111.111111 |
|             3 | Finance         |   53666.666667 |
|             4 | Marketing       |   67250.000000 |
|             5 | HR              |   51500.000000 |
|             6 | Operations      |   63500.000000 |
|             7 | Consulting      |   83000.000000 |
|             8 | Administration  |   58500.000000 |
+---------------+-----------------+----------------+







