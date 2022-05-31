<!-- 
Modellizzare la struttura di una tabella per memorizzare tutti i dati riguardanti una università:
- sono presenti diversi Dipartimenti (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
- ogni Dipartimento offre più Corsi di Laurea (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
- ogni Corso di Laurea prevede diversi Corsi (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
- ogni Corso può essere tenuto da diversi Insegnanti;
- ogni Corso prevede più appelli d'Esame;
- ogni Studente è iscritto ad un solo Corso di Laurea;
- ogni Studente può iscriversi a più appelli di Esame;
- per ogni appello d'Esame a cui lo Studente ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente Pensiamo a quali entità (tabelle) creare per il nostro database e cerchiamo poi di stabilirne le relazioni.
 -->


# DB_Universita

## Dipartimenti

id:                             PK BIGINT AUTO_INCREMENT NOTNULL UNIQUE        
nome:                           VARCHAR(100) NOTNULL INDEX
sede:                           VARCHAR(50)  NULL
indirizzo:                      VARCHAR(100) NULL
sito_web:                       VARCHAR(255) NULL
descrizione:                    TEXT NULL

## Corsi_di_laurea
id:                             PK BIGINT AUTO_INCREMENT NOTNULL UNIQUE                             
dipartimento_id:                FK NOTNULL
nome:                           VARCHAR(100) NOTNULL INDEX
descrizione:                    TEXT NULL
## Corsi
id:                             PK BIGINT AUTO_INCREMENT NOTNULL UNIQUE  
corso_di_laurea_id:             FK NOTNULL
nome:                           VARCHAR(35) NOTNULL INDEX
cfu:                            TINYINT NOTNULL
descrizione:                    TEXT NULL

## Professori
id:                            PK BIGINT AUTO_INCREMENT NOTNULL UNIQUE  
corso_id:                      FK NOTNULL
nome:                          VARCHAR(35) NOTNULL INDEX
cognome:                       VARCHAR(35) NOTNULL INDEX
email:                         VARCHAR(50) NOTNULL


## Appelli_di_esame
id:                           PK BIGINT AUTO_INCREMENT NOTNULL UNIQUE  
professore_id:                FK NOTNULL 
studente_id:                  FK NOTNULL
data:                         DATE NOTNULL INDEX
voto:                         TINYINT NOTNULL
note:                         TEXT NULL

## Studenti
id:                           PK BIGINT AUTO_INCREMENT NOTNULL UNIQUE  
matricola:                    VARCHAR(50) AUTO_INCREMENT UNIQUE NOTNULL INDEX
nome:                         VARCHAR(50) NOTNULL INDEX
cognome:                      VARCHAR(50) NOTNULL INDEX
anno di nascita:              DATE NOTNULL
iscrizione:                   DATE NOTNULL
email:                        VARCHAR(50) NOTNULL
telefono:                     NOTNULL
esami_sostenuti:              TINYINT NULL
esami_da_sostenere:           TINYINT NULL
cfu_totali:                   SMALLINT NULL

