# EasyCRUDboard

application.properties 설정

spring.datasource.driverClassName=org.mariadb.jdbc.Driver

spring.datasource.url=jdbc:mariadb://localhost:3306/board

spring.datasource.username=스키마계정

spring.datasource.password=비밀번호


테스트 데이터 프로시저 생성

DELIMITER $$

CREATE PROCEDURE testDataInsert()
BEGIN
    DECLARE i INT DEFAULT 1;

    WHILE i <= 120 DO
        INSERT INTO board(title, content)
          VALUES(concat('제목',i), concat('내용',i));
        SET i = i + 1;
    END WHILE;
END$$
DELIMITER $$
