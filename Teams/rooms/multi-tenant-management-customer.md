---
title: Partnerverwaltung für Kunden
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: dstrome
ms.date: 06/09/2022
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
ms.openlocfilehash: b186adbf0df84e0739abd4675cfcf1437885d365
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2022
ms.locfileid: "67023886"
---
# <a name="partner-management-for-customers"></a>Partnerverwaltung für Kunden

Die Partnerverwaltung im Teams-Räume Managed (TRM)-Dienst ermöglicht Es Kunden, den Zugriff und die Zuständigkeiten nahtlos an eine oder mehrere Partnerorganisationen zu delegieren. Partner können nur Räume verwalten, denen sie zugewiesen sind.

## <a name="on-boarding-partners"></a>On-Boarding-Partner
   Laden Sie Partner über das TRM-Portal ein, die Beziehung zwischen Ihrer Organisation und dem Mandanten der Partnerorganisation herzustellen.

### <a name="invitation-to-partner"></a>Einladung zum Partner

   Bei dieser Methode sollten Sie den Domänennamen des Partners kennen (z. B. Contoso.com).

**So initiieren Sie die Einladung** 

1. Melden Sie sich beim Teams-Räume verwalteten Portal als Administrator für verwaltete Dienste an.
1. Wechseln **Sie zu "Einstellungen" >** **"Partner**", und wählen Sie dann **"Partner hinzufügen" aus.**
1. Geben Sie den Domänennamen in die erste Zeile ein.
1. Konfigurieren Sie die Anzahl der Tage, bis die Einladung abläuft, indem Sie eine ganze Zahl zwischen 1 und 30 eingeben.
1. Konfigurieren Sie die Ereignisse, für die eine Genehmigung des Änderungssteuerelements erforderlich ist. Standardmäßig sind alle Steuerelemente auf "**Automatische Genehmigung**" festgelegt.

   > [!NOTE]
   > *Derzeit ist nur die automatische Genehmigung verfügbar.*
   > 
   >  1.  *Manuelle Genehmigung:* Wenn der Partner die Aktion ausführt, wird eine Genehmigungsanforderung generiert, die der Kunde überprüfen und genehmigen kann. Die Aktion wird erst implementiert, wenn die Anforderung genehmigt wurde.
   >  
   >  1. *Automatische Genehmigung:* Wenn der Partner die Aktion ausführt, wird keine Genehmigungsanforderung generiert und die Aktion sofort implementiert.
     
1. Wählen Sie **"Weiter" aus.**
1. Weisen Sie Räume zu, die der Partner verwaltet, und wählen Sie dann **"Weiter**" aus.
1. Um fortzufahren, überprüfen Sie die Bedingungen, und wählen Sie **"Ich stimme zu."**
1. Überprüfen Sie die Details der Einladung.
1. Wählen Sie **"Partner hinzufügen"** aus, um die Einladung zu senden.

Die Einladung wird zur Überprüfung an die Mandantenmanager in der Partnerinstanz gesendet. Der erste Partnerbenutzer, der die Einladung akzeptiert, stellt die Verknüpfung zwischen dem Partner und Ihrem Mandanten her und weist primäre Administratoren zu. Es gibt keine spezielle Zuordnung mit dem Benutzer, der den Link herstellt, was die Flexibilität bei einer erneuten Zuweisung des Benutzers ermöglicht. In der primären Administratorrolle muss immer mindestens ein Benutzer vorhanden sein.

Informationen zum Verwalten von Benutzern in der primären Administratorrolle finden Sie unter ["Verwaltung mit mehreren Mandanten für Partner"](multi-tenant-management-partner.md).

## <a name="off-boarding-partners"></a>Off-Boarding-Partner

**So entfernen Sie einen Partner**

1. Melden Sie sich beim TRM-MTM-Portal als MMR-Administrator an.
1. Navigieren Sie zu **"Einstellungen > Partner".**
1. Wählen Sie den Partner aus, den Sie entfernen möchten.
1. Wählen Sie im Detailbereich "Kunden" die Option **"Partner entfernen" aus.**
1. Wählen Sie **Löschen** aus. 
1. Wählen Sie an der Bestätigungsaufforderung zum Beenden der Zuordnung zwischen Ihnen und dem Kundenmandanten die Option **"Löschen"** aus.

## <a name="managing-partner-roles"></a>Verwalten von Partnerrollen

Partnerrollen ermöglichen Es Ihrem Partner, Zuständigkeiten genauer an zusätzliches Personal zu delegieren. Das Konzept dieser Rollen entspricht dem in der [rollenbasierten Zugriffssteuerung](microsoft-teams-rooms-premium-rbac.md) beschriebenen Konzept. Es ist wichtig zu beachten, dass sich Partnerrollen von Ihren benutzerdefinierten Rollen unterscheiden. 

Die **Primäre Administratorrolle** ist die einzige integrierte Rolle für jeden hinzugefügten Partner. Diese Rolle verfügt über fast alle Berechtigungen für die Räume, die Sie diesem Partner für den TRM-Dienst zugewiesen haben (siehe [Tabelle 1](#table-1)). Wenn Sie beispielsweise über Räume auf der ganzen Welt verfügen und einen Partner zum Verwalten aller US-Räume zuweisen, kann der primäre Administrator nur Berechtigungen für diese Räume verwalten und delegieren. In diesem Fall haben die primären Administratoren für diesen Partner keinen Einblick in Räume außerhalb der USA. 

### <a name="adding-primary-admins-to-partner"></a>Hinzufügen von primären Administratoren zum Partner

Wenn Sie bereits eine Einladung an einen Partner gesendet haben und weitere Räume delegieren möchten, können Sie der Partneradministratorrolle Räume hinzufügen.

**So fügen Sie einem vorhandenen Partner neue Räume hinzu**

1. Melden Sie sich beim TRM-MTM-Portal als MMR-Administrator an.
1. Wechseln Sie zu **Einstellungen > Rollen.**
1. Wählen Sie  **Partnerrollen aus.** 
1. Wählen Sie die **Rolle des primären Administrators** für den entsprechenden Partnernamen aus.
1. Wählen Sie im Rollenbereich **"Aufgaben" aus**.
1. Wählen Sie die Zuweisung **"Zugewiesene Administratoren" aus** .
1. Wählen Sie im Aufgabenbereich "Zugewiesene Administratoren" den Eintrag **"Bereich**" aus.
1. Wählen Sie **"Bearbeiten" aus**.
1. Suchen Sie nach den Räumen, die Sie hinzufügen möchten, und wählen Sie den gewünschten Raum aus.
1. Um die Änderungen zu bestätigen, wählen Sie **"Speichern" aus**.

### <a name="table-1"></a>Tabelle 1

|Feature|Berechtigung|**MMR-Admin**|**Websiteleiter**|**Site Tech**|**Partneradministrator**|
| :- | :- | :- | :- | :- | :- |
|Zimmer|Anzeigen| &#10004;|&#10004;|&#10004;|&#10004;|
||Ändern|&#10004;|&#10004;|&#10004;|&#10004;|
||Rücksetztaste|&#10004;||||
||Downloadschlüssel|&#10004;|&#10004;|&#10004;||
||Registrierung aufheben|&#10004;|&#10004;|&#10004;||
||Erstellen |&#10004;|&#10004;|||
|Gruppenverwaltung|Anzeigen|&#10004;|&#10004;||&#10004;|
||Ändern|&#10004;|&#10004;|||
||Erstellen |&#10004;|&#10004;|||
|Ringverwaltung aktualisieren|Anzeigen|&#10004;|&#10004;||&#10004;|
||Ändern|&#10004;|&#10004;||&#10004;|
|Berichte|Anzeigen|&#10004;|&#10004;||&#10004;|
||Erstellen eines Kundenvorfalls|&#10004;|&#10004;|&#10004;|&#10004;|
|Ticketverwaltung|Anzeigen|&#10004;|&#10004;|&#10004;|&#10004;|
||Aktualisieren|&#10004;|&#10004;|&#10004;|&#10004;|
|MMR-Einstellungen|Anzeigen|&#10004;||||
||Ändern|&#10004;||||
|Rollenverwaltung|Anzeigen |&#10004;|||&#10004;|
||Ändern|&#10004;|||&#10004;|

## <a name="security"></a>Sicherheit

Als Endkunde behalten Sie die Kontrolle über den Zugriff auf Ihre Daten und können jederzeit einen Partner vollständig entfernen. 

Mit der Funktion für delegierten Zugriff erhält ein Partner außerhalb des TRM-Dienstportals keine weiteren Berechtigungen. Alle Daten, die im TRM-Dienst vorhanden sind, die von anderen Microsoft-Produkten abgeleitet werden, werden jedoch als Daten im TRM-Dienst betrachtet. Während Beispielsweise Anrufqualitätsberichte von Teams-Anrufqualitätsdaten abgeleitet werden, befinden sich alle Daten im TRM-Portal im Berechtigungsbereich. 

AAD oder dem Teams Admin Center oder einem anderen Microsoft-Produkt werden keine Berechtigungen erteilt. Darüber hinaus haben Partner keinen Zugriff darauf, Räume anzuzeigen oder zu ändern, die nicht im Einladungsbereich definiert sind. 

Die Daten befinden sich im Mandanten des Kunden und werden nicht in den Mandanten des Partners kopiert. 

Das MTM-Portal verwendet die Azure AD-Authentifizierung, um die Anmeldeinformationen des Partners zu überprüfen. Beachten Sie, dass die Authentifizierungsrichtlinien des Kunden zu diesem Zeitpunkt nicht für den Partner gelten. Wenn der Kunde beispielsweise über eine mehrstufige Authentifizierungsrichtlinie verfügt, wird diese nicht in den Partner übersetzt. 

Informationen zum Abrufen von Protokollen für Partneraktivitäten finden Sie unter [Überwachung](multi-tenant-auditing.md). 

> [!NOTE]
> AAD-Überwachung und O365-Überwachung erfassen keine Protokolle aus dem TRM-Portal. 
