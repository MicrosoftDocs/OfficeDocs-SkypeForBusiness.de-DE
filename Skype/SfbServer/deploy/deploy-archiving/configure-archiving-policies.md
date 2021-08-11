---
title: Konfigurieren von Archivierungsrichtlinien für Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie anfängliche Archivierungsrichtlinien für Skype for Business Server Benutzer konfigurieren.'
ms.openlocfilehash: 9db20eefd26de31eb01ab25d4ef7596319459b68be3f76ce95ba0b355122eee8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312123"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a>Konfigurieren von Archivierungsrichtlinien für Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie anfängliche Archivierungsrichtlinien für Skype for Business Server Benutzer konfigurieren.
  
In Skype for Business Server verwenden Sie Richtlinien, um die Archivierung für die interne und externe Kommunikation für Benutzer zu aktivieren und zu deaktivieren, die auf Skype for Business Server verwaltet werden. Dazu gehört Folgendes:
  
- Eine globale Richtlinie, die standardmäßig beim Bereitstellen von Skype for Business Server
    
- Optionale Richtlinien auf Standortebene, die angeben, wie die Archivierung für einen bestimmten Standort implementiert wird
    
- Optionale Richtlinien auf Benutzerebene, die angeben, wie die Archivierung für bestimmte Benutzer implementiert wird
    
Sie richten archivierungsrichtlinien anfänglich ein, wenn Sie die Archivierung bereitstellen, aber Sie können Richtlinien nach der Bereitstellung ändern, hinzufügen und löschen. In Skype for Business Server Systemsteuerung können Sie die Seite **"Archivierungsrichtlinien"** der Gruppe **"Archivierung und Überwachung"** verwenden, um Richtlinien auf globaler, Standort- und Benutzerebene zu verwalten.
  
> [!NOTE]
> Um die Implementierung der Archivierung zu steuern, müssen Sie Optionen angeben, z. B. ob Chats oder Konferenzen archiviert werden sollen, die Verwendung des kritischen Modus und Bereinigungsoptionen. Standardmäßig sind keine Optionen in der globalen Archivierungskonfiguration oder einer Archivierungskonfiguration für Standorte oder Pools aktiviert. Sie sollten alle geeigneten Optionen angeben, bevor Sie die Archivierung für die interne oder externe Kommunikation aktivieren. Ausführliche Informationen finden Sie unter [Konfigurieren von Archivierungsoptionen für Skype for Business Server.](configure-archiving-options.md) 
  
> [!NOTE]
> Wenn Sie die Integration von Microsoft Exchange für Ihre Bereitstellung aktivieren, steuern Exchange In-Place Aufbewahrungsrichtlinien, ob die Archivierung für die Benutzer aktiviert ist, die in Exchange verwaltet werden und deren Postfächer In-Place Haltebereich haben. 
  
Ausführliche Informationen zur Funktionsweise von Archivierungsrichtlinien, einschließlich der Hierarchie für globale, Standort- und Benutzerrichtlinien, finden Sie unter [Plan for archiving in Skype for Business Server.](../../plan-your-deployment/archiving/archiving.md) Ausführliche Informationen zum Verwalten von Richtlinien nach der Bereitstellung finden Sie unter [Verwalten von Archivierungsrichtlinien in Skype for Business Server](../../manage/archiving/policies.md).
  
## <a name="global-policy"></a>Globale Richtlinie

Wenn Sie Ihre Front-End-Server bereitstellen, erstellt Skype for Business Server eine globale Richtlinie für die Archivierung. Standardmäßig ist die Archivierung in der globalen Richtlinie deaktiviert. Die globale Richtlinie steuert, ob die Archivierung für die interne und externe Kommunikation für Die gesamte Bereitstellung aktiviert ist, es sei denn, Sie richten Standort- oder Benutzerrichtlinien ein, die die globale Richtlinie außer Kraft setzen, oder wenn Sie Microsoft Exchange Integration für einige oder alle Benutzer verwenden. Wenn Sie Microsoft Exchange Integration verwenden, gilt die globale Richtlinie nicht für Benutzer, die in Exchange verwaltet werden und die Postfächer in In-Place Haltebereich setzen.
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a>Konfigurieren der globalen Richtlinie für die Archivierung für Skype for Business Server Archivierungsdatenbanken

1. Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungsrichtlinie**.
    
4. Klicken Sie auf der Seite **Archivierungsrichtlinie** auf **Global**, auf **Edit** und dann auf **Details anzeigen**.
    
5. Führen Sie im Abschnitt **Bearbeiten der Archivierungsrichtlinie – Global** folgende Aktionen aus:
    
   - Geben Sie im Feld **Name** einen neuen Namen für die globale Richtlinie ein, wenn Sie den Standardnamen "Global" nicht verwenden möchten. 
    
   - Geben Sie in **der Beschreibung** Informationen dazu an, was die Richtlinie ist (z. B. globale Richtlinie für  *divisionName*  .
    
   - Um die Archivierung der internen Kommunikation für alle Standorte und Benutzer zu kontrollieren, die nicht explizit durch eine Standort- oder Benutzerrichtlinie gesteuert wird, aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**.
    
   - Um die Archivierung der externen Kommunikation für alle Standorte und Benutzer zu kontrollieren, die nicht explizit durch eine Standort- oder Benutzerrichtlinie gesteuert wird, aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**.
    
6. Klicken Sie auf **Commit**.
    
## <a name="site-policies"></a>Websiterichtlinien

Sie können die Archivierung für bestimmte Standorte aktivieren oder deaktivieren, indem Sie für jeden dieser Standorte eine Archivierungsrichtlinie erstellen. Eine Standortrichtlinie setzt die globale Richtlinie außer Kraft, benutzerrichtlinien setzen jedoch Standortrichtlinien außer Kraft. Archivierungsrichtlinien gelten nur, wenn Sie Microsoft Exchange Integration nicht verwenden oder wenn Sie Microsoft Exchange Integration verwenden, aber einige Benutzer haben, die nicht in Exchange verwaltet werden und ihre Postfächer In-Place Haltebereich haben.
  
### <a name="create-an-archiving-policy-for-a-site"></a>Erstellen einer Archivierungsrichtlinie für einen Standort

1. Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.
    
3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungsrichtlinie**.
    
    Ausführliche Informationen zur Funktionsweise von Archivierungsrichtlinien, einschließlich der Hierarchie für globale, Standort- und Benutzerrichtlinien, finden Sie unter [Plan for archiving in Skype for Business Server.](../../plan-your-deployment/archiving/archiving.md)
    
4. Klicken Sie auf **Neu** und anschließend auf **Standortrichtlinie**.
    
5. Klicken Sie im Dialogfeld **Standort auswählen** auf den Standort, auf den die Richtlinie angewendet werden soll.
    
6. Führen Sie unter **Neue Archivierungsrichtlinie** die folgenden Aktionen aus:
    
   - Geben Sie im Feld **Name** den Namen für die Standortrichtlinie an. 
    
   - Geben Sie im Feld **Beschreibung** Informationen zum Verwendungszweck der Standortrichtlinie an (z. B. Standortrichtlinie für Redmond).
    
   - Aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**, um die Archivierung der internen Kommunikation für den angegebenen Standort zu aktivieren oder zu deaktivieren.
    
   - Aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**, um die Archivierung der externen Kommunikation für den angegebenen Standort zu aktivieren oder zu deaktivieren.
    
7. Klicken Sie auf **Commit ausführen**.
    
## <a name="user-policies"></a>Benutzerrichtlinien

Sie können die Archivierung für bestimmte Benutzer aktivieren oder deaktivieren, indem Sie eine Archivierungsrichtlinie für Benutzer erstellen und konfigurieren und dann die Richtlinie auf bestimmte Benutzer oder Benutzergruppen anwenden. Benutzerrichtlinien setzen alle globalen Richtlinien oder Standortrichtlinien außer Kraft. Archivierungsrichtlinien gelten nur, wenn Sie Microsoft Exchange Integration nicht verwenden oder wenn Sie Microsoft Exchange Integration verwenden, aber einige Benutzer haben, die nicht in Exchange verwaltet werden und ihre Postfächer In-Place Haltebereich haben.
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a>Konfigurieren einer Archivierungsrichtlinie für Benutzer, die auf Skype for Business Server verwaltet werden

1. Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungsrichtlinie**.
    
4. Klicken Sie auf **Neu** und anschließend auf **Benutzerrichtlinie**.
    
5. Führen Sie unter **Neue Archivierungsrichtlinie** die folgenden Schritte aus:
    
   - Geben Sie im Feld **Name** den Namen der Benutzerrichtlinie an. 
    
   - Machen Sie im Feld **Beschreibung** nähere Angaben zur Art der Benutzerrichtlinie (z. B. Benutzerrichtlinie für die Rechtsabteilung).
    
   - Um die Archivierung der internen Kommunikation für die Benutzerrichtlinie zu kontrollieren, aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**.
    
   - Um die Archivierung der externen Kommunikation für die Benutzerrichtlinie zu kontrollieren, aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**.
    
6. Klicken Sie auf **Commit**.
    
Benutzerrichtlinien wirken sich nur auf Benutzer aus, denen eine solche Richtlinie zugewiesen wurde.
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a>Anwenden einer Skype for Business Server Archivierungsrichtlinie auf einen Benutzer

1. Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 
    
3. Klicken Sie auf der linken Navigationsleiste auf **Benutzer**, und suchen Sie dann nach dem Benutzerkonto, das Sie konfigurieren möchten.
    
4. Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.
    
5. Wählen Sie unter **"Bearbeiten Skype for Business Server Benutzers** unter **Archivierungsrichtlinie"** die Archivierungsbenutzerrichtlinie aus, die Sie anwenden möchten.
    
    > [!NOTE]
    > Die **\<Automatic\>** Einstellungen gelten für die Standardeinstellungen für die Serverinstallation. Diese Einstellungen werden automatisch vom Server angewendet.
  
6. Klicken Sie auf **Commit ausführen**.
    

