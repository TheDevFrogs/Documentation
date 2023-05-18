```plantuml
@startuml

:Coordonateur: as Admin
:Étudiant: as Student
:Enseignant: as Teacher 
:Correcteur: as Corector


Teacher -|> Corector

'Tous'
    (Athentification) as (Athentification)
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

    Admin -- ClassManagement
    ClassManagement ..> CreateClass
    ClassManagement ..> ModifyClass
    ClassManagement ..> DeleteClass

    ClassManagement ..> GroupManagement
    
    GroupManagement ..> CreateGroup
    GroupManagement ..> ModifyGroup
    GroupManagement ..> DeleteGroup

'Enseignant'
    (Gestion Travaux) as (CorrectorWorkManagement)
    (Gestion Travail) as (TeacherWorkManagement)
    (Créer Travail) as (CreateWork)
    (Modifier Travail) as (ModifyWork)
    (Supprimer Travail) as (DeleteWork)
'Correcteur'
    (Gestion Correction) as (CorrectionManagement)
    (Télécharger classe) as (DownloadClass)
    (Télécharger groupe) as (DownloadStudent)
    (Télécharger étudiant) as (DownloadStudent)
    (Remettre Correction) as (DeliverCorrection)
'Etudiant'
    (Gestion Remise) as (StudentWorkManagement)
    (Remette Travail) as (Remette Travail)







@enduml
```

## Abstraction
- Remise : Travail remis par un étudiant
- Correction : Correction d'un travail remis par un enseignant ou un correcteur
- Travail : Travail à remettre par un étudiant créer par un enseignant