# sql
create table iiii(n integer);
delete from iiii;
CREATE OR REPLACE FUNCTION fibonacci (n INTEGER) 
   RETURNS INTEGER AS $$ 
DECLARE
   counter INTEGER := 0 ; 
   i INTEGER := 0 ; 
   j INTEGER := 1 ;
BEGIN
   IF (n < 1) THEN
      RETURN 0 ;
   END IF; 
   
   LOOP 
      EXIT WHEN counter = n ; 
      counter := counter + 1 ; 
      SELECT j, i + j INTO i,   j ;
      insert into iiii values(j);
   END LOOP ; 
   
   RETURN i ;
END ; 
$$ LANGUAGE plpgsql;

select fibonacci(10)

select * from iiii
