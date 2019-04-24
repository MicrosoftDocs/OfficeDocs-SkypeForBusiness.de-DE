---
title: Konfigurieren von Archivierungsrichtlinien für Skype Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 'Zusammenfassung: Lesen Sie in diesem Thema erfahren, wie die ursprüngliche Archivierungsrichtlinien für Skype für Business Server-Benutzer konfigurieren.'
ms.openlocfilehash: 88840d10cbd7a71b32b5079a8600018b97e8b0c3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233244"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a>Konfigurieren von Archivierungsrichtlinien für Skype Business Server
 
**Zusammenfassung:** Lesen Sie in diesem Thema erfahren, wie die ursprüngliche Archivierungsrichtlinien für Skype für Business Server-Benutzer konfigurieren.
  
In Skype für Business Server verwenden Sie Richtlinien zum Aktivieren und Deaktivieren der Archivierung für interne Kommunikation und externen Kommunikation für Benutzer, die auf Skype für Business Server verwaltet werden. Dazu gehört Folgendes:
  
- Eine globale Richtlinie, die standardmäßig erstellt wird, bei der Bereitstellung von Skype für Business Server
    
- Optionale Richtlinien auf Standortebene, die festlegen, wie die Archivierung für einen bestimmten Standort implementiert wird.
    
- Optionale Richtlinien auf Benutzerebene, die angeben, wie die Archivierung für bestimmte Benutzer implementiert wird
    
Zunächst eingerichtet werden Archivierungsrichtlinien, wenn Sie die Archivierung bereitstellen, jedoch können Sie ändern, hinzufügen und Löschen von Benutzerrichtlinien nach der Bereitstellung. Die Seite **Archivierungsrichtlinie** der Gruppe der **Archivierung und Überwachung** können Sie in Skype Business Server-Systemsteuerung Richtlinien auf globaler, Standort- und Benutzerebene verwalten.
  
> [!NOTE]
> Um die Implementierung der Archivierung zu steuern, müssen Sie die Optionen, z. B., ob archiviert Sofortnachrichten oder Konferenzen, die Verwendung des kritischen Modus und Löschung Optionen angeben. Standardmäßig sind keine Optionen in der globalen Archivierungskonfiguration oder jede Website oder poolarchivierungskonfiguration aktiviert. Sie sollten alle entsprechende Optionen angeben, vor dem Aktivieren der Archivierung für interne oder externe Kommunikation. Weitere Informationen hierzu finden Sie unter [Konfigurieren von Archivierungsoptionen für Skype für Business Server](configure-archiving-options.md). 
  
> [!NOTE]
> Wenn Sie Microsoft Exchange-Integration für die Bereitstellung, Exchange In-Place Hold Policies Steuerelement aktivieren, ob Archivierung aktiviert ist, für die Benutzer, die sich auf Exchange befinden und haben ihren Postfächern zu Compliance-Archiv platzieren. 
  
Ausführliche Informationen zu wie Archivierungsrichtlinien arbeiten, einschließlich der Hierarchie für globale, Standort- und Benutzerrichtlinien, finden Sie unter [Planen für die Archivierung in Skype für Business Server](../../plan-your-deployment/archiving/archiving.md). Ausführliche Informationen zum Verwalten von Richtlinien nach der Bereitstellung finden Sie unter [Verwalten von Archivierungsrichtlinien in Skype für Business Server](../../manage/archiving/policies.md).
  
## <a name="global-policy"></a>Globale Richtlinie

Wenn Sie die Front-End-Server bereitstellen, erstellt Skype für Business Server eine globale Richtlinie für die Archivierung. Archivierung ist standardmäßig in der globalen Richtlinie deaktiviert. Die globale Richtlinie steuert, ob Archivierung für die internen und externen Kommunikation für die gesamte Bereitstellung aktiviert ist, es sei denn, Sie von Standort- oder Richtlinien festgelegt, die die globale Richtlinie außer Kraft setzen, oder wenn Sie Microsoft Exchange-Integration für einige oder alle verwenden Ihre Benutzer. Wenn Sie Microsoft Exchange-Integration verwenden, die globale Richtlinie gilt nicht für alle Benutzer, die in Exchange verwaltet werden, und haben die Postfächer, die Compliance-Archiv platzieren.
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a>Konfigurieren der globalen Richtlinie für die Archivierung für Skype für Business Server-Archivierungsdatenbanken

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.
    
4. Klicken Sie auf der Seite **Archivierungsrichtlinie** auf **Global**, auf **Bearbeiten** und dann auf **Details anzeigen**.
    
5. Führen Sie im Abschnitt **Bearbeiten der Archivierungsrichtlinie – Global** folgende Aktionen aus:
    
   - Geben Sie im Feld **Name** einen neuen Namen für die globale Richtlinie ein, wenn Sie den Standardnamen „Global“ nicht verwenden möchten. 
    
   - Geben Sie im Feld **Beschreibung**Informationen dazu, was die Richtlinie (z. B. globale Richtlinie für die *DivisionName* .
    
   - Um die Archivierung der internen Kommunikation für alle Standorte und Benutzer zu kontrollieren, die nicht explizit durch eine Standort- oder Benutzerrichtlinie gesteuert werden, aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**.
    
   - Um die Archivierung der externen Kommunikation für alle Standorte und Benutzer zu kontrollieren, die nicht explizit durch eine Standort- oder Benutzerrichtlinie gesteuert werden, aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**.
    
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="site-policies"></a>Standortrichtlinien

Sie können aktivieren oder Deaktivieren der Archivierung für bestimmte Standorte, indem Sie eine Archivierungsrichtlinie für die einzelnen Websites erstellen. Eine Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch Benutzerrichtlinien überschreiben Standortrichtlinien. Archivierungsrichtlinien gelten nur, wenn Sie nicht Microsoft Exchange-Integration verwenden oder, wenn Sie Microsoft Exchange-Integration verwenden, aber haben einige Benutzer befinden sich nicht auf Exchange-haben ihren Postfächern Compliance-Archiv platzieren.
  
### <a name="create-an-archiving-policy-for-a-site"></a>Erstellen einer Archivierungsrichtlinie für einen Standort

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.
    
3. Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.
    
    Ausführliche Informationen zu wie Archivierungsrichtlinien arbeiten, einschließlich der Hierarchie für globale, Standort- und Benutzerrichtlinien, finden Sie unter [Planen für die Archivierung in Skype für Business Server](../../plan-your-deployment/archiving/archiving.md).
    
4. Klicken Sie auf **Neu** und anschließend auf **Standortrichtlinie**.
    
5. Klicken Sie im Dialogfeld **Standort auswählen** auf den Standort, auf den die Richtlinie angewendet werden soll.
    
6. Führen Sie unter **Neue Archivierungsrichtlinie** die folgenden Aktionen aus:
    
   - Geben Sie im Feld **Name** den Namen für die Standortrichtlinie an. 
    
   - Geben Sie im Feld **Beschreibung** Informationen zum Verwendungszweck der Standortrichtlinie an (z. B. Standortrichtlinie für Redmond).
    
   - Aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**, um die Archivierung der internen Kommunikation für den angegebenen Standort zu aktivieren oder zu deaktivieren.
    
   - Aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**, um die Archivierung der externen Kommunikation für den angegebenen Standort zu aktivieren oder zu deaktivieren.
    
7. Klicken Sie auf **Commit ausführen**.
    
## <a name="user-policies"></a>Benutzerrichtlinien

Sie können aktivieren oder Deaktivieren der Archivierung für bestimmte Benutzer durch Erstellen und konfigurieren eine Archivierungsrichtlinie für Benutzer, und wenden Sie dann die Richtlinie auf bestimmte Benutzer oder Benutzergruppen. Richtlinien für Benutzer außer Kraft setzen globale Richtlinie oder websiterichtlinien. Archivierungsrichtlinien gelten nur, wenn Sie nicht Microsoft Exchange-Integration verwenden oder, wenn Sie Microsoft Exchange-Integration verwenden, aber haben einige Benutzer befinden sich nicht auf Exchange-haben ihren Postfächern Compliance-Archiv platzieren.
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a>Konfigurieren Sie eine Archivierungsrichtlinie für Benutzer in Skype für Business Server verwaltet

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.
    
4. Klicken Sie auf **Neu** und anschließend auf **Benutzerrichtlinie**.
    
5. Führen Sie unter **Neue Archivierungsrichtlinie** die folgenden Aktionen aus:
    
   - Geben Sie im Feld **Name** den Namen der Benutzerrichtlinie an. 
    
   - Machen Sie im Feld **Beschreibung** nähere Angaben zur Art der Benutzerrichtlinie (z. B. Benutzerrichtlinie für die Rechtsabteilung).
    
   - Um die Archivierung der internen Kommunikation für die Benutzerrichtlinie zu kontrollieren, aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**.
    
   - Um die Archivierung der externen Kommunikation für die Benutzerrichtlinie zu kontrollieren, aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**.
    
6. Klicken Sie auf **Commit ausführen**.
    
Benutzerrichtlinien wirken sich nur auf Benutzer aus, denen eine solche Richtlinie zugewiesen wurde.
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a>Anwenden einer Skype für Business Server Archivierungsrichtlinie zu einem Benutzer

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer** und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.
    
4. Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.
    
5. Wählen Sie in **Skype für Business Server-Benutzer bearbeiten** unter **Archivierungsrichtlinie**Benutzerrichtlinie, die Sie anwenden möchten.
    
    > [!NOTE]
    > Die ** \<automatische\> ** Einstellungen gelten die Standardeinstellungen für Server-Installation. Diese Einstellungen werden vom Server automatisch übernommen.
  
6. Klicken Sie auf **Commit ausführen**.
    

