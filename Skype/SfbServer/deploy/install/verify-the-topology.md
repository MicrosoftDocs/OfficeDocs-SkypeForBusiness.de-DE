---
title: Überprüfen der Topologie in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie überprüfen können, ob die Skype for Business Server-Topologie und die Active Directory-Server wie erwartet funktionieren. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverCenter unter: herunter.'
ms.openlocfilehash: aa631e5b08ff8cbe9cb6db17009f286dcc975679
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41791713"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a>Überprüfen der Topologie in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie überprüfen können, ob die Skype for Business Server-Topologie und die Active Directory-Server wie erwartet funktionieren. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server vom [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)herunter.
  
Nachdem Sie die Topologie veröffentlicht haben und die Systemkomponenten von Skype for Business Server auf jedem der Server in der Topologie installiert sind, können Sie überprüfen, ob die Topologie wie erwartet funktioniert. Dies umfasst die Überprüfung, ob die Konfiguration an alle Active Directory-Server weitergegeben wurde, damit die gesamte Domäne weiß, dass Skype for Business in der Domäne verfügbar ist. Sie können die Schritte 1 bis 5 in einer beliebigen Reihenfolge ausführen. Die Schritte 6, 7 und 8 müssen jedoch wie in der Abbildung dargestellt nacheinander und nach den Schritten 1 bis 5 ausgeführt werden. Die Überprüfung der Topologie ist Schritt 8 von 8.
  
![Übersichtsdiagramm.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>Testen der Front-End-Poolbereitstellung

Der letzte Schritt besteht darin, den Front-End-Pool zu testen und zu bestätigen, dass Skype for Business-Clients miteinander kommunizieren können. 
  
### <a name="add-users-and-verify-client-connectivity"></a>Hinzufügen von Benutzern und Überprüfen der Clientkonnektivität

1. Verwenden Sie Active Directory-Computer und-Benutzer zum Hinzufügen des Active Directory-Benutzerobjekts der Administratorrolle für die Skype for Business Server-Bereitstellung (auf der Skype for Business Server-Systemsteuerung installiert ist) zur **CSAdministrator** -Gruppe.
    
    > [!IMPORTANT]
    > Wenn Sie die entsprechenden Benutzer und Gruppen nicht zur CsAdministors-Gruppe hinzufügen, erhalten Sie eine Fehlermeldung, wenn Sie die Skype for Business Server-Systemsteuerung öffnen, die lautet: "nicht autorisiert: Zugriff verweigert aufgrund eines Autorisierungs Fehlers bei der rollenbasierten Zugriffssteuerung (RBAC) ." 
  
2. Wenn das Benutzerobjekt derzeit angemeldet ist, melden Sie es ab und wieder an, um die neue Gruppenzuweisung zu registrieren.
    
    > [!NOTE]
    > Das Benutzerkonto kann nicht der lokale Administrator eines Servers sein, auf dem Skype for Business Server ausgeführt wird. 
  
3. Verwenden Sie das Administratorkonto, um sich bei dem Computer anzumelden, auf dem die Skype for Business Server-Systemsteuerung installiert ist.
    
4. Starten Sie die Skype for Business Server-Systemsteuerung, und geben Sie dann die Anmeldeinformationen ein, wenn Sie dazu aufgefordert werden. In der Skype for Business Server-Systemsteuerung werden Bereitstellungsinformationen angezeigt.
    
5. Klicken Sie in der linken Navigationsleiste auf **Topologie**, und stellen Sie dann sicher, dass der Dienststatus einen Computer mit einem grünen Pfeil anzeigt und ein grünes Häkchen für den Replikationsstatus neben jeder Skype for Business-Server Rolle steht, die bereitgestellt und online geschaltet wurde. 
    
6. Klicken Sie in der linken Navigationsleiste auf **Benutzer** und dann auf **Benutzer aktivieren**. 
    
7. Klicken Sie auf der **neuen Skype for Business Server-Benutzer** Seite auf **Hinzufügen**.
    
8. Wenn Sie Suchparameter für die zu ermittelnden Objekte definieren möchten, aktivieren Sie auf der Seite **Aus Active Directory auswählen** die Option **Suchen** und klicken Sie optional auf **Filter hinzufügen**. Alternativ können Sie auch die Option **LDAP-Suche** aktivieren und einen LDAP-Ausdruck eingeben, um die zurückgegebenen Objekte zu filtern oder einzuschränken. Klicken Sie auf **Suchen**, nachdem Sie die gewünschten Suchoptionen festgelegt haben.
    
9. Wählen Sie im Bereich mit den Suchergebnissen alle hinzuzufügenden Benutzer aus und klicken Sie dann auf **OK**.
    
10. Auf der **neuen Benutzerseite für Skype for Business Server** befinden sich die von Ihnen ausgewählten Benutzer in der Ansicht **Benutzer** . Wählen Sie in der Liste **Benutzer einem Pool zuweisen** den Server aus, auf dem sich die Benutzer befinden sollen.
    
    Im Folgenden finden Sie eine Liste der Optionen, die Sie zum Konfigurieren der Objekte verwenden können.
    
    - **SIP-URI des Benutzers generieren**
    
    - **Telefonie**
    
    - **Anschluss-URI**
    
    - **Konferenzrichtlinie**
    
    - **Clientversionsrichtlinie**
    
    - **PIN-Richtlinie**
    
    - **Externe Zugriffsrichtlinie**
    
    - **Archivierungsrichtlinie**
    
    - **Standortrichtlinie**
    
    - **Clientrichtlinie**
    
    Wenn Sie die grundlegenden Funktionen testen möchten, wählen Sie die gewünschte Option für die **SIP-URI-Einstellung des Benutzers generieren** aus (die anderen Optionen in der Konfiguration verwenden Standardeinstellungen), und klicken Sie dann auf **aktivieren**, wie in der Abbildung dargestellt.
    
     ![Aktivieren von Benutzern in der Systemsteuerung](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. Es wird eine Zusammenfassungsseite angezeigt, auf der ein Häkchen in der Spalte **Aktiviert** darauf hinweist, dass die Benutzer eingerichtet sind. In der Spalte **SIP-Adresse** wird die Adresse angezeigt, die Sie zur Konfiguration der Benutzeranmeldung benötigen.
    
     ![Benutzer, die der Skype for Business Server-Systemsteuerung hinzugefügt wurden](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. Melden Sie einen Benutzer bei einem Computer an, der mit der Domäne verknüpft ist, und einen weiteren Benutzer bei einem anderen Computer in der Domäne.
    
13. Installieren Sie den Skype for Business-Client auf jedem der beiden Clientcomputer, und stellen Sie dann sicher, dass sich beide Benutzer bei Skype for Business Server anmelden können und Sofortnachrichten senden können.
    

