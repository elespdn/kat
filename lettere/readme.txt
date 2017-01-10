STEP 1
------
Eliminare numeri, tutto ciò che c'è dentro le parentesi quadre, le divisioni di linea con | e le parentesi
\d|\[\w+\]|\||\(|\)


STEP 2
------
sostituire doppi spazi con singoli


PROBLEMI
--------
durante la trascrizione, non inserire spazi vicino alle parentesi quadre


COSA VOGLIO
-----------

esempio:
[1ra] Sanctissimo et | r(everendissimo) padre mio | in Chr(ist)o dolce | Yh(es)u. Io K(aterina), in|degna et mise||rabile v(ost)ra fil|guola, s(er)va e schiava di s(er)vi de | Yh(es)u Ch(rist)o, sc(r)ivo a voi nel p(re)cioso | sangue suo. Co(n) desiderio de ve|dervi pastore buono, conside||rando me, babbo mio dolce, ch(e) | il luppo ne porta le pecorelle | v(ost)re et no(n) si trova chi le rede|misca. 

----->
 tokenize su spazi, includendo | e [...] nella parola successiva, non considerando parentesi e considerando punteggiatura da sola, tipo:
 \|\s(\w)*(\(\w+\)(\w)*)*|(\w)*\(\w+\)(\w)*|\w+(\|)*\w+
----->
[1ra] 
Sanctissimo
et 
| 
r(everendissimo) 
padre 
mio 
| 
in 
Chr(ist)o 
dolce 
| 
Yh(es)u
. 
Io 
K(aterina)
, 
in|degna 
et 
mise||rabile 
v(ost)ra 
fil|guola
----->
 in 't' lasciarla così, in 'n' normalizzare 
 \d|\[\w+\]|\||\(|\)
----->



