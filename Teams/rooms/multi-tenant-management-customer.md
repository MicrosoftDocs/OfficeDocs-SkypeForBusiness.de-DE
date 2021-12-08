---
title: Partnerverwaltung für Kunden
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: dstrome
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Partnerverwaltung für Kunden.
f1keywords: ''
ms.openlocfilehash: 84d15f43ff49565dbba915470ea618a69ff74ee8
ms.sourcegitcommit: c8951fe3504c1776d7aec14b79605aaf5d317e7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2021
ms.locfileid: "61331234"
---
# <a name="partner-management-for-customers"></a>Partnerverwaltung für Kunden


Die Partnerverwaltung im Teams-Räume Managed (TRM)-Dienst ermöglicht es Kunden, Zugriff und Zuständigkeiten nahtlos an eine oder viele Partnerorganisationen zu delegieren. Partner können nur Räume verwalten, die ihnen zugewiesen wurden. 

## <a name="on-boarding-partners"></a>Onboarding-Partner
   Laden Sie Partner über das TRM-Portal ein, um die Beziehung zwischen Ihrer Organisation und dem Mandanten der Partnerorganisation zu richten. 

### <a name="invitation-to-partner"></a>Einladung an Partner

   Bei dieser Methode sollte der Partner die *UPNs* der Benutzer bereitstellen, die die Ihnen zugewiesenen primären Administratoren sein sollen. 

**So initiieren Sie die Einladung** 

1. Melden Sie sich als MMR-Administrator Teams-Räume verwalteten Portal an.
1. Wechseln Sie **Einstellungen >** **Partner**, und wählen Sie dann Partner **hinzufügen aus.**
1. Geben Sie in der ersten Zeile den Namen und den UPN der primären Administratoren ein.
1. Wählen Sie **zur Bestätigung Kontakt** hinzufügen aus.
1. Führen Sie einen der folgenden Schritte aus:
   - Wenn Sie einen weiteren Benutzer hinzufügen möchten, wiederholen Sie Schritt 4.
   - Um einen Benutzer zu löschen, wählen Sie das Bin-Symbol auf der rechten Seite des Benutzers aus.

    > [!NOTE]
    > Es ist nicht möglich, Gruppen oder Verteilerlisten zu verwenden, da die Einladung an den UPN gebunden ist.

1. Wählen Sie **Weiter aus.**
1. Konfigurieren Sie die Ereignisse, für die eine Änderungssteuerelementgenehmigung erforderlich ist. Standardmäßig ist für alle Steuerelemente die automatische **Genehmigung festgelegt.**

   > [!NOTE]
   > *Derzeit ist nur die automatische Genehmigung verfügbar.*
   > 
   >  1.  *Manuelle Genehmigung:* Wenn der Partner die Aktion ausführt, wird eine Genehmigungsanforderung generiert, die der Kunde überprüfen und genehmigen soll. Die Aktion wird erst implementiert, wenn die Anforderung genehmigt wurde.
   >  
   >  1. *Automatische Genehmigung:* Wenn der Partner die Aktion ausführt, wird keine Genehmigungsanforderung generiert, und die Aktion wird sofort implementiert.
     
1. Wählen Sie **Weiter aus.**
1. Weisen Sie räume zu, die der Partner verwalten wird, und wählen Sie dann **Weiter aus.**
1. Um fortzufahren, überprüfen Sie die Bedingungen, und wählen Sie **Ich stimme zu aus.**
1. Überprüfen Sie die Details der Einladung.
1. Wählen Sie **Partner hinzufügen aus,** um die Einladung zu senden.

Die Einladung ist für jeden Benutzer eindeutig und unabhängig. Der erste Partnerbenutzer, der die Einladung akzeptiert, richtet den Link zwischen dem Partner und Ihrem Mandanten ein. Es gibt keine spezielle Verknüpfung mit dem Benutzer, die den Link einrichten. Dies ermöglicht Flexibilität, wenn der Benutzer neu zugewiesen wird. Nachfolgende Benutzer, die die Einladung annehmen, werden automatisch der Rolle "Primäre Administratoren" zugewiesen. Die primäre Administratorrolle muss immer mindestens einen Benutzer haben.

Informationen zum Verwalten von Benutzern in der primären Administratorrolle finden Sie unter [Verwaltung von mehreren Mandanten für Partner.](multi-tenant-management-partner.md)


## <a name="off-boarding-partners"></a>Offboardingpartner

**So entfernen Sie einen Partner**

1. Melden Sie sich als MMR-Administrator beim TRM-MTM-Portal an.
1. Navigieren Sie zu **Einstellungen > Partner.**
1. Wählen Sie den Partner aus, den Sie entfernen möchten.
1. Wählen Sie im Detailbereich des Kunden Partner **entfernen aus.**
1. Wählen Sie **Löschen** aus. 
1. Wählen Sie an der Bestätigungsaufforderung zum Beenden der Zuordnung zwischen Ihrem und dem Kunden mandanten die Option **Löschen aus.**

## <a name="managing-partner-roles"></a>Verwalten von Partnerrollen

Partnerrollen ermöglichen es Ihrem Partner, Zuständigkeiten präziser an zusätzliche Mitarbeiter zu delegieren. Das Konzept dieser Rollen ist das gleiche wie unter [Rollenbasierte Zugriffssteuerung beschrieben.](microsoft-teams-rooms-premium-rbac.md) Es ist wichtig zu beachten, dass sich Partnerrollen von Ihren benutzerdefinierten Rollen unterscheiden. 

Die **Primäre Administratorrolle** ist die einzige integrierte Rolle für jeden hinzugefügten Partner. Diese Rolle besitzt fast alle Berechtigungen für die Räume, die Sie diesem Partner für den TRM-Dienst zugewiesen haben (siehe [Tabelle 1](#table-1)). Wenn Sie beispielsweise Räume auf der ganzen Welt haben und einen Partner zum Verwalten aller US-Räume zuweisen, kann der primäre Administrator berechtigungen für diese Räume nur verwalten und delegieren. In diesem Fall haben die primären Administratoren dieses Partners keinen Einblick in Räume außerhalb der USA. 

### <a name="adding-primary-admins-to-partner"></a>Hinzufügen von primären Administratoren zu Einem Partner

Wenn Sie bereits eine Einladung an einen Partner gesendet haben und diesem Administrator weitere Benutzer hinzufügen möchten, können Sie diese zur Rolle des Partneradministrators hinzufügen. Dadurch wird effektiv eine Einladung an die hinzugefügten Benutzer übermittelt.

**So fügen Sie einem vorhandenen Partner neue Benutzer hinzu**

1. Melden Sie sich als MMR-Administrator beim TRM-MTM-Portal an.
1. Wechseln Sie **zu Einstellungen > Rollen.**
1. Wählen Sie  **Partnerrollen aus.** 
1. Wählen Sie **die Rolle des primären** Administrator für den entsprechenden Partnernamen aus.
1. Wählen Sie im Rollenbereich Aufgaben **aus.**
1. Wählen Sie die **Aufgabe Eingeladene Administratoren** aus. 
1. Wählen Sie im Aufgabenbereich Eingeladene Administratoren die Option **Mitglieder aus.**
1. Wählen Sie **Bearbeiten aus.**
1. Geben Sie den UPN des neuen Benutzers ein, und wählen Sie **Kontakt hinzufügen aus.**
1. Um die Änderungen zu bestätigen, wählen Sie **Speichern aus.**

<!--To remove users for an existing partner~~

1. ~~Login to the TRM-MTM portal as a MMR administrator~~
1. ~~Navigate to **Settings > Roles**~~
1. ~~Select the **Partner roles** tab~~
1. ~~Select the **Primary admin** role for the corresponding Partner name~~
1. ~~In the role pane, select the **Assignments** tab~~
1. ~~Select the **Invited admins** assignment~~ 
1. ~~In the Invited admins assignment pane, select the **Members** tab~~
1. ~~Select the **Edit** icon~~
1. ~~Enter the UPN of the new user and select **Add contact**~~
1. ~~Click **Save** to confirm the changes-->




### <a name="table-1"></a>Tabelle 1

|Feature|Berechtigung|**MMR Admin**|**Websiteleiter**|**Site Tech**|**Partneradministrator**|
| :- | :- | :- | :- | :- | :- |
|Räume|Anzeigen|||||
||Ändern|||||
||Rücksetztaste|||||
||Downloadschlüssel|||||
||Registrierung aufenrolln|||||
|Gruppenverwaltung|Erstellen |||||
||Anzeigen|||||
||Ändern|||||
|Verwaltung von Update-Ringen|Erstellen |||||
||Anzeigen|||||
||Ändern|||||
|Berichte|Anzeigen|||||
|Ticketverwaltung|Kundenvorfall erstellen|||||
||Anzeigen|||||
||Aktualisieren|||||
|MMR Einstellungen|Anzeigen|||||
||Ändern|||||
|Rollenverwaltung|Anzeigen |||||
||Ändern|||||





## <a name="security"></a>Sicherheit

Als Endbenutzer behalten Sie die Kontrolle über den Zugriff auf Ihre Daten und können einen Partner jederzeit vollständig entfernen. 

Mit dem Feature für delegierten Zugriff hat ein Partner keine weiteren Rechte außerhalb des TRM-Dienstportals. Alle Daten, die in dem TRM-Dienst enthalten sind, der von anderen Microsoft-Produkten abgeleitet wird, werden jedoch als Daten im TRM-Dienst betrachtet. Während beispielsweise Berichte zur Anrufqualität aus den Teams der Anrufqualität abgeleitet werden, befinden sich alle Daten im TRM-Portal im Berechtigungsbereich. 

Es werden keine Berechtigungen für AAD, das Teams Admin Center oder ein anderes Microsoft-Produkt erteilt. Darüber hinaus haben Partner keinen Zugriff auf das Anzeigen oder Ändern von Räumen, die nicht im Einladungsbereich definiert sind. 

Die Daten befinden sich im Mandanten des Kunden und werden nicht in den Mandanten des Partners kopiert. 

Das MTM-Portal verwendet Azure AD Authentifizierung, um die Anmeldeinformationen des Partners zu überprüfen. Beachten Sie, dass die Authentifizierungsrichtlinien des Kunden derzeit nicht für den Partner gelten. Wenn der Kunde beispielsweise über eine Mehrstufige Authentifizierungsrichtlinie verfügt, wird diese nicht für den Partner übersetzt. 

Informationen zum Pullen von Protokollen über Partneraktivitäten finden Sie unter [Überwachung.](multi-tenant-auditing.md) 

> [!NOTE]
> AAD- und O365-Überwachung erfassen keine Protokolle aus dem TRM-Portal. 
