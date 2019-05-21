---
title: Konfigurieren von Archivierungsrichtlinien für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie die anfänglichen Archivierungsrichtlinien für Skype for Business Server-Benutzer konfigurieren.'
ms.openlocfilehash: 9d4fc7bd27440688f981ac9d05b1e47750ad7867
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286560"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a>Konfigurieren von Archivierungsrichtlinien für Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie die anfänglichen Archivierungsrichtlinien für Skype for Business Server-Benutzer konfigurieren.
  
In Skype for Business Server verwenden Sie Richtlinien, um die Archivierung für interne Kommunikation und externe Kommunikation für Benutzer zu aktivieren und zu deaktivieren, die in Skype for Business Server verwaltet werden. Dazu gehört Folgendes:
  
- Eine globale Richtlinie, die standardmäßig bei der Bereitstellung von Skype for Business Server erstellt wird
    
- Optionale Richtlinien auf Standortebene, die festlegen, wie die Archivierung für einen bestimmten Standort implementiert wird.
    
- Optionale Richtlinien auf Benutzerebene, die angeben, wie die Archivierung für bestimmte Benutzer implementiert wird
    
Sie haben zunächst Archivierungsrichtlinien eingerichtet, wenn Sie die Archivierung bereitstellen, Sie können aber nach der Bereitstellung Richtlinien ändern, hinzufügen und löschen. In der Skype for Business Server-Systemsteuerung können Sie die Seite **Archivierungsrichtlinie** der Gruppe **Archivierung und Überwachung** verwenden, um Richtlinien auf globaler, Website-und Benutzerebene zu verwalten.
  
> [!NOTE]
> Um die Implementierung der Archivierung zu steuern, müssen Sie Optionen angeben, beispielsweise ob Sie Chatnachrichten oder Konferenzen archivieren, die Verwendung des kritischen Modus und Bereinigungsoptionen verwenden möchten. Standardmäßig sind keine Optionen in der globalen Archivierungskonfiguration oder einer Standort-oder Pool Archivierungskonfiguration aktiviert. Sie sollten alle geeigneten Optionen angeben, bevor Sie die Archivierung für die interne oder externe Kommunikation aktivieren. Ausführliche Informationen finden Sie unter [Konfigurieren von Archivierungsoptionen für Skype for Business Server](configure-archiving-options.md). 
  
> [!NOTE]
> Wenn Sie die Microsoft Exchange-Integration für Ihre Bereitstellung aktivieren, Steuern Exchange-in-situ-Speicherrichtlinien, ob die Archivierung für die Benutzer aktiviert ist, die sich in Exchange befinden, und dass ihre Postfächer in-situ-Speicher abgelegt werden. 
  
Ausführliche Informationen zur Funktionsweise von Archivierungsrichtlinien, einschließlich der Hierarchie für Global-, Website-und Benutzerrichtlinien, finden Sie unter [Planen der Archivierung in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md). Details zum Verwalten von Richtlinien nach der Bereitstellung finden Sie unter [Verwalten von Archivierungsrichtlinien in Skype for Business Server](../../manage/archiving/policies.md).
  
## <a name="global-policy"></a>Globale Richtlinie

Wenn Sie Ihre Front-End-Server bereitstellen, erstellt Skype for Business Server eine globale Richtlinie für die Archivierung. Standardmäßig ist die Archivierung in der globalen Richtlinie deaktiviert. Mit der globalen Richtlinie wird gesteuert, ob die Archivierung für die interne und externe Kommunikation für Ihre gesamte Bereitstellung aktiviert ist, es sei denn, Sie richten Website-oder Benutzerrichtlinien ein, die die globale Richtlinie außer Kraft setzen, oder wenn Sie die Microsoft Exchange-Integration für einige oder alle von Ihre Benutzer. Wenn Sie die Microsoft Exchange-Integration verwenden, gilt die globale Richtlinie nicht für alle Benutzer, die sich in Exchange befinden und die Postfächer in-situ-Speicherplatz gespeichert haben.
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a>Konfigurieren der globalen Richtlinie für die Archivierung von Skype for Business Server-Archivierungsdatenbanken

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 
    
3. Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.
    
4. Klicken Sie auf der Seite **Archivierungsrichtlinie** auf **Global**, auf **Bearbeiten** und dann auf **Details anzeigen**.
    
5. Führen Sie im Abschnitt **Bearbeiten der Archivierungsrichtlinie – Global** folgende Aktionen aus:
    
   - Geben Sie im Feld **Name** einen neuen Namen für die globale Richtlinie ein, wenn Sie den Standardnamen „Global“ nicht verwenden möchten. 
    
   - Geben Sie in **Beschreibung**Informationen zu den Richtlinien an (beispielsweise globale Richtlinie für ** divisionname.
    
   - Um die Archivierung der internen Kommunikation für alle Standorte und Benutzer zu kontrollieren, die nicht explizit durch eine Standort- oder Benutzerrichtlinie gesteuert werden, aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**.
    
   - Um die Archivierung der externen Kommunikation für alle Standorte und Benutzer zu kontrollieren, die nicht explizit durch eine Standort- oder Benutzerrichtlinie gesteuert werden, aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**.
    
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="site-policies"></a>Standortrichtlinien

Sie können die Archivierung für bestimmte Websites aktivieren oder deaktivieren, indem Sie für jede dieser Websites eine Archivierungsrichtlinie erstellen. Eine Website Richtlinie überschreibt die globale Richtlinie, aber Benutzerrichtlinien überschreiben Website Richtlinien. Archivierungsrichtlinien gelten nur, wenn Sie die Microsoft Exchange-Integration nicht verwenden, oder wenn Sie die Microsoft Exchange-Integration verwenden, aber einige Benutzer haben, die nicht in Exchange gespeichert sind und deren Postfächer in einem Speicherplatz abgelegt werden.
  
### <a name="create-an-archiving-policy-for-a-site"></a>Erstellen einer Archivierungsrichtlinie für einen Standort

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.
    
3. Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.
    
    Ausführliche Informationen zur Funktionsweise von Archivierungsrichtlinien, einschließlich der Hierarchie für Global-, Website-und Benutzerrichtlinien, finden Sie unter [Planen der Archivierung in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).
    
4. Klicken Sie auf **Neu** und anschließend auf **Standortrichtlinie**.
    
5. Klicken Sie im Dialogfeld **Standort auswählen** auf den Standort, auf den die Richtlinie angewendet werden soll.
    
6. Führen Sie unter **Neue Archivierungsrichtlinie** die folgenden Aktionen aus:
    
   - Geben Sie im Feld **Name** den Namen für die Standortrichtlinie an. 
    
   - Geben Sie im Feld **Beschreibung** Informationen zum Verwendungszweck der Standortrichtlinie an (z. B. Standortrichtlinie für Redmond).
    
   - Aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**, um die Archivierung der internen Kommunikation für den angegebenen Standort zu aktivieren oder zu deaktivieren.
    
   - Aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**, um die Archivierung der externen Kommunikation für den angegebenen Standort zu aktivieren oder zu deaktivieren.
    
7. Klicken Sie auf **Commit ausführen**.
    
## <a name="user-policies"></a>Benutzerrichtlinien

Sie können die Archivierung für bestimmte Benutzer aktivieren oder deaktivieren, indem Sie eine Archivierungsrichtlinie für Benutzer erstellen und konfigurieren und dann die Richtlinie auf bestimmte Benutzer oder Benutzergruppen anwenden. Benutzerrichtlinien überschreiben alle globalen Richtlinien oder Website Richtlinien. Archivierungsrichtlinien gelten nur, wenn Sie die Microsoft Exchange-Integration nicht verwenden, oder wenn Sie die Microsoft Exchange-Integration verwenden, aber einige Benutzer haben, die nicht in Exchange gespeichert sind und deren Postfächer in einem Speicherplatz abgelegt werden.
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a>Konfigurieren einer Archivierungsrichtlinie für Benutzer, die in Skype for Business Server verwaltet werden

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 
    
3. Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.
    
4. Klicken Sie auf **Neu** und anschließend auf **Benutzerrichtlinie**.
    
5. Führen Sie unter **Neue Archivierungsrichtlinie** die folgenden Aktionen aus:
    
   - Geben Sie im Feld **Name** den Namen der Benutzerrichtlinie an. 
    
   - Machen Sie im Feld **Beschreibung** nähere Angaben zur Art der Benutzerrichtlinie (z. B. Benutzerrichtlinie für die Rechtsabteilung).
    
   - Um die Archivierung der internen Kommunikation für die Benutzerrichtlinie zu kontrollieren, aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**.
    
   - Um die Archivierung der externen Kommunikation für die Benutzerrichtlinie zu kontrollieren, aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**.
    
6. Klicken Sie auf **Commit ausführen**.
    
Benutzerrichtlinien wirken sich nur auf Benutzer aus, denen eine solche Richtlinie zugewiesen wurde.
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a>Anwenden einer Skype for Business Server-Archivierungsrichtlinie auf einen Benutzer

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer** und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.
    
4. Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.
    
5. Wählen Sie in **Skype for Business Server-Benutzer bearbeiten** unter **Archivierungsrichtlinie**die Archivierungs Benutzerrichtlinie aus, die Sie anwenden möchten.
    
    > [!NOTE]
    > Die ** \<automatischen\> ** Einstellungen gelten für die standardmäßigen Server Installationseinstellungen. Diese Einstellungen werden vom Server automatisch übernommen.
  
6. Klicken Sie auf **Commit ausführen**.
    

