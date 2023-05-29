```plantuml
@startuml

left to right direction

:Coordonateur: as Admin
:Étudiant: as Student
:Enseignant: as Teacher 
:Correcteur: as Corector


Teacher -|> Corector

'Tous'
    (Athentification) as (Athentification)
    Teacher -up- Athentification
    Corector -up- Athentification
    Student -up- Athentification
    Admin -up- Athentification
package RemiseTrvaux{

'Coordonateur'
    (Gestion Classe) as (ClassManagement)
    (Créer Classe) as (CreateClass)
    (Modifier Classe) as (ModifyClass)
    (Supprimer Classe) as (DeleteClass)

    (Gestion Groupe) as (GroupManagement)
    (Créer Groupe) as (CreateGroup)
    (Modifier Groupe) as (ModifyGroup)
    (Supprimer Groupe) as (DeleteGroup)
    

    (Associer Enseignant) as (AssociateTeacher)
    (Associer Étudiant) as (AssociateStudent)
    (Associer Correcteur) as (AssociateCorrector)

    Admin -- ClassManagement
    ClassManagement ..> CreateClass
    ClassManagement ..> ModifyClass
    ClassManagement ..> DeleteClass

    Admin -- GroupManagement
    
    GroupManagement ..> CreateGroup
    GroupManagement ..> ModifyGroup
    GroupManagement ..> DeleteGroup
    GroupoManagement ..> AssociateTeacher
    GroupManagement ..> AssociateStudent
    GroupManagement ..> AssociateCorrector

'Enseignant'
    (Gestion Travail) as (TeacherWorkManagement)
    (Créer Travail) as (CreateWork)
    (Modifier Travail) as (ModifyWork)
    (Supprimer Travail) as (DeleteWork)


    Teacher -- TeacherWorkManagement
    TeacherWorkManagement ..> CreateWork
    TeacherWorkManagement ..> ModifyWork
    TeacherWorkManagement ..> DeleteWork

'Correcteur'
    (Gestion Correction) as (CorrectionManagement)
    (Télécharger classe) as (DownloadClass)
    (Télécharger groupe) as (DownloadStudentGroup)
    (Télécharger étudiant) as (DownloadStudent)
    (Remettre Correction) as (DeliverCorrection)

    Corector -- CorrectionManagement
    CorrectionManagement ..> DownloadClass
    CorrectionManagement ..> DownloadStudent
    CorrectionManagement ..> DownloadStudentGroup
    CorrectionManagement ..> DeliverCorrection
'Etudiant'
    (Gestion Remise) as (StudentWorkManagement)
    (Remette Remise) as (HandWork)
    (Telecharger Correction) as (DownloadCorrection)
    Student -- StudentWorkManagement
    StudentWorkManagement ..> HandWork
    StudentWorkManagement ..> DownloadCorrection

}
@enduml
```

## Abstraction
- Remise : Travail remis par un étudiant
- Correction : Correction d'un travail remis par un enseignant ou un correcteur
- Travail : Travail à remettre par un étudiant créer par un enseignant