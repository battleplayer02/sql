# sql
create table iiii(n integer);<br>
delete from iiii;<br>
CREATE OR REPLACE FUNCTION fibonacci (n INTEGER) <br>
   RETURNS INTEGER AS $$ <br>
DECLARE<br>
   counter INTEGER := 0 ; <br>
   i INTEGER := 0 ; <br>
   j INTEGER := 1 ;<br>
BEGIN<br>
   IF (n < 1) THEN<br>
      RETURN 0 ;<br>
   END IF; <br>
   
   LOOP <br>
      EXIT WHEN counter = n ; <br>
      counter := counter + 1 ; <br>
      SELECT j, i + j INTO i,   j ;<br>
      insert into iiii values(j);<br>
   END LOOP ; <br>
   <br>
   RETURN i ;<br>
END ; <br>
$$ LANGUAGE plpgsql;<br>
<br>
select fibonacci(10)<br>
<br>
select * from iiii<br>
