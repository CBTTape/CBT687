# CBT687
Converted to GitHub via [cbt2git](https://github.com/wizardofzos/cbt2git)

This is still a work in progress. 
Due to amazing work by Alison Zhang and Jake Choi repos are no longer deleted.

```
//***FILE 687 is from Jose Maria (Chema) Alvarez and contains       *   FILE 687
//*           a package to compare catalogs mentioned in VVDS'es    *   FILE 687
//*           on DASD volumes, and see if they are actually         *   FILE 687
//*           connected to the real catalog in the system.          *   FILE 687
//*                                                                 *   FILE 687
//*           A CLIST and and ISPF skeleton are provided.  The      *   FILE 687
//*           output of the CLIST is a job, which is presented      *   FILE 687
//*           to you in ISPF edit.  Running this job enables you    *   FILE 687
//*           to compare your referenced catalogs in a VVDS to      *   FILE 687
//*           those that are actually connected to the system.      *   FILE 687
//*           Then you can decide if any adjustments are necessary. *   FILE 687
//*                                                                 *   FILE 687
//*           Chema Alvarez / z/OS Sysprog                          *   FILE 687
//*           Caja Cantabria/Santander/Spain                        *   FILE 687
//*           e-mail:  jalvarez@casyc.es                            *   FILE 687
//*                                                                 *   FILE 687
//*  Sample generated job (partial):                                *   FILE 687
//*                                                                 *   FILE 687
//*   //useridD  JOB (P,EXP),MSGCLASS=X,CLASS=A  etc.               *   FILE 687
//*   //PASO1    EXEC PGM=IDCAMS,REGION=3M                          *   FILE 687
//*   //SYSPRINT DD SYSOUT=*                                        *   FILE 687
//*   //C1 DD DSN=CATALOG.OS390.MASTER,DISP=SHR                     *   FILE 687
//*    * * * *                                                      *   FILE 687
//*   //C4 DD DSN=MVSUSER.USERCAT,DISP=SHR                          *   FILE 687
//*    * * * *                                                      *   FILE 687
//*   //V1 DD DSN=SYS1.VVDS.VOS39M1, IN CATALOG.OS390.MASTER        *   FILE 687
//*   //        DISP=SHR,UNIT=SYSDA,VOL=SER=OS39M1                  *   FILE 687
//*    * * * *                                                      *   FILE 687
//*   //V7 DD DSN=SYS1.VVDS.VDATA04, IN MVSUSER.USERCAT             *   FILE 687
//*   //        DISP=SHR,UNIT=SYSDA,VOL=SER=DATA04                  *   FILE 687
//*    * * * *                                                      *   FILE 687
//*   //SYSIN    DD *                                               *   FILE 687
//*    DIAGNOSE ICFCATALOG INFILE(C1) COMPAREDD(V1)                 *   FILE 687
//*    * * * *                                                      *   FILE 687
//*    DIAGNOSE VVDS INFILE(V1) COMPAREDD(C1)                       *   FILE 687
//*    * * * *                                                      *   FILE 687
//*   /*                                                            *   FILE 687
//*                                                                 *   FILE 687
//*  Sample error message:                                          *   FILE 687
//*                                                                 *   FILE 687
//*     DIAGNOSE VVDS INFILE(V7) COMPAREDD(C4)                      *   FILE 687
//*    IDC11367I THE FOLLOWING VVDS REFERENCED CATALOGS             *   FILE 687
//*    WERE NOT ENCOUNTERED:                                        *   FILE 687
//*      MVSRES.MASTER.CATALOG                                      *   FILE 687
//*    IDC0001I FUNCTION COMPLETED, HIGHEST CONDITION CODE WAS 4    *   FILE 687
//*                                                                 *   FILE 687
```
