---
title: Mandantenübergreifende Kundenverwaltung für Partner
author: donnah007
ms.author: v-donnahill
ms.date: 07/25/2022
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
description: Mult-Tenant-Kundenverwaltung für Partner.
f1keywords: ''
ms.openlocfilehash: 23b0460d5f59830ea00522ac001b7f7524ad2f45
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2022
ms.locfileid: "67024118"
---
# <a name="multi-tenant-customer-management-for-partners"></a>Mandantenübergreifende Kundenverwaltung für Partner

Die Mehrinstanzenverwaltung (Multi-Tenant Management, MTM) im Teams-Räume Managed (TRM)-Dienst hilft Partnerorganisationen, mehrere Kunden an einem Ort mit ihren eigenen Domänenanmeldeinformationen zu verwalten. Partnerbenutzern werden nur Kundenräume angezeigt, die ihnen zugewiesen sind, um sie zu verwalten. Es ist möglich, benutzerdefinierte Rollen für jeden Kunden im MTM-Mandanten anzuwenden, sodass Partnerorganisationen die Berechtigungen für die Ressourcen des Kunden präzise steuern können. 

Auf das MTM-Portal kann über diesen [Link](https://partner.rooms.microsoft.com/) zugegriffen werden.

> [!Note] 
> Partnerorganisationen können ihre eigenen Räume nicht über das MTM-Portal verwalten. Diese Räume können im [TRM-Portal](https://portal.rooms.microsoft.com/) verwaltet werden. 

## <a name="pre-requisites-for-managing-your-customers-through-the-mtm-experience"></a>Voraussetzungen für die Verwaltung Ihrer Kunden über die MTM-Erfahrung

Um Zugriff auf das MTM-Portal zu erhalten, muss Ihre Organisation als Elite-Partner für den TRM-Dienst eingebunden sein. So werden Sie Elite-Partnerkontakt askelite@microsoft.com.

## <a name="on-boarding-customers"></a>On-Boarding-Kunden

Um Kunden über das TRM-MTM-Portal zu verwalten, muss eine Beziehung zwischen dem Mandanten der Partnerorganisation und dem Kunden über eine vom Kunden gesendete Einladung hergestellt werden. 

## <a name="tenant-managers"></a>Mandantenmanager

Diese integrierte Rolle kann nur im TRM-MTM-Portal konfiguriert werden. Mit dieser Rolle können Sie eine Gruppe von Benutzern zuweisen, die Einladungen annehmen, aber nicht an der Verwaltung von Kundenräumen beteiligt sind. Es wird empfohlen, die Rolle zu konfigurieren. Andernfalls können nur Benutzer mit der Rolle "Verwalteter Dienstadministrator" in Ihrem Mandanten Einladungen annehmen.

**So konfigurieren Sie Mandantenmanager**
 
1.  Melden Sie sich beim TRM-MTM-Portal entweder als globaler Administrator oder als Verwalteter Dienstadministrator an.
2.  Wechseln Sie zu Mandantenmanagern.
3.  Wählen Sie **"Mandantenmanager hinzufügen"** aus.
4.  Suchen Sie im Detailbereich nach den Benutzern oder Sicherheitsgruppen.
5.  Wählen Sie den Benutzer oder die Gruppe aus.
6.  Klicken Sie auf **Hinzufügen**.

### <a name="invitation-from-the-customer"></a>Einladung des Kunden

Der Partner sollte den Domänennamen für Kunden angeben. Nur die Rollen "Globaler Administrator", "Verwalteter Dienstadministrator" und "Mandanten-Manager" können die Einladung sehen und annehmen, wenn sie sich beim TRM-MTM-Portal anmelden. 

> [!Note]
> Obwohl diese Rollen Einladungen und Mandantenmetadaten auf hoher Ebene anzeigen können, werden die Daten des Kunden erst angezeigt, wenn Ihnen eine Rolle für diesen Kunden zugewiesen wurde.

Details zur Kundeneinladung werden in der [Mandantenübergreifenden Verwaltung für Kunden](multi-tenant-management-customer.md) beschrieben.

**So akzeptieren Sie eine ausstehende Einladung**

1. Melden Sie sich beim TRM-MTM-Portal als globaler Administrator, Verwalteter Dienstadministrator oder Mandanten-Manager an.
1. Wechseln Sie zu **"Mandanten"**.
1. Wählen Sie die Einladung mit dem Status "Ausstehend" aus.
1. Überprüfen Sie die Einladungsdetails.
1. Weisen Sie Benutzer zu, die die primären Administratoren dieses Kunden sein sollen.
1. Wählen Sie **"Annehmen"** aus, um die Partner-Kundenbeziehung herzustellen.

   Wenn Sie **"Verweigern** " auswählen, wird die Einladung gelöscht.

   > [!Note]
   > Es gibt keine dauerhafte Zuordnung zum Benutzer, der die Einladung annimmt.

   > [!Note]
   > *Wenn die Einladung versehentlich abgelehnt wird, muss der Kunde eine neue Einladung erstellen.* 

**So überprüfen Sie die Konfiguration oder fügen weitere primäre Administratoren für einen Mandanten hinzu**

1. Wählen Sie den Kunden **in der** Mandantenliste aus.
1. Wählen Sie im Detailbereich **"Primäre Administratoren" aus**.
1. Suchen Sie nach dem Benutzer oder der Gruppe.
1. Wählen Sie **"Hinzufügen"** aus, um die Auswahl zu bestätigen.

## <a name="off-boarding-customers"></a>Offboarding-Kunden

Um einen Kunden aus dem Board zu nehmen, müssen Sie diese **aus der** Mandantenliste entfernen.

**So entfernen Sie einen Kunden** 

1. Melden Sie sich beim TRM-MTM-Portal als primärer Administrator für den Kunden an, den Sie entfernen möchten.
1. Wechseln Sie zu **"Mandanten"**.
1. Wählen Sie den Kunden aus, den Sie entfernen möchten.
1. Wählen Sie im Detailbereich "Kunden" die Option **"Kunde entfernen" aus**.
1. Wählen Sie in der Bestätigungsaufforderung " **Löschen** " aus, um die Zuordnung zwischen Ihnen und dem Kundenmandanten zu beenden.

## <a name="managing-partner-roles"></a>Verwalten von Partnerrollen

Partnerrollen ermöglichen die Delegierung von Zuständigkeiten an zusätzliches Personal. Das Konzept dieser Rollen ist das gleiche wie in der [rollenbasierten Zugriffssteuerung](microsoft-teams-rooms-premium-rbac.md) beschrieben, jedoch im Kontext jedes Kunden. Darüber hinaus ist es wichtig zu beachten, dass sich Partnerrollen von den Rollen des Kunden unterscheiden. Die Partnerrollen können vom Kunden gelöscht werden. 

Die Rolle " **Primäre Administratoren** " ist die einzige integrierte Rolle für jeden integrierten Kunden und verfügt über fast alle Berechtigungen – im Kontext des Kunden – für den TRM-Dienst (siehe Tabelle 1). Partner**-Rollenberechtigungen erstrecken sich nur bis zu den vom Kunden festgelegten Räumen. Wenn der Kunde beispielsweise eine globale Organisation ist und dem Partner die Verwaltung aller US-Räume zuweist, kann der primäre Administrator nur Berechtigungen für diese Räume verwalten und delegieren. Der Partner hat keinen Einblick in andere Räume, die der Kunde möglicherweise in anderen Ländern hat. 

**So verwalten Sie Benutzer in der **Partnerrolle** für einen Kunden**

1. Wechseln Sie zu **Einstellungen > Rollen**. 
1. Wählen Sie den Kunden aus der Dropdownliste aus, für den Sie die Partnerrolle bearbeiten möchten.
1. Wählen Sie die integrierte Rolle " **Primäre Administratoren** " aus der Liste aus.
1. Wählen Sie **"Aufgaben" aus.**
1. Wählen Sie in der Liste **"Zugewiesene Administratoren" aus.**
1. Mitglieder auswählen **.**
1. Wählen Sie **"Bearbeiten" aus.** 
1. Suchen Sie nach dem Benutzer oder der Sicherheitsgruppe, den Sie in der Suchleiste hinzufügen möchten.
1. Wählen Sie den Benutzer oder die Gruppe aus.
1. Wählen Sie **"Speichern"** aus, um die Änderungen zu bestätigen.

### <a name="managing-custom-partner-roles-for-a-customer"></a>Verwalten von benutzerdefinierten Partnerrollen für einen Kunden

Als Partner können Sie benutzerdefinierte Rollen für Ihre betrieblichen Anforderungen erstellen. Sie können z. B. eine Helpdesk-Rolle erstellen, die nur über Berechtigungen für die Vorfallverwaltung verfügen sollte. 

**So verwalten Sie Rollen**

1. Wechseln Sie zu **Einstellungen > Rollen**. 
1. Wählen Sie den Kunden aus dem Dropdownmenü aus, für den Sie die Partnerrolle bearbeiten möchten.
1. Erstellen Sie eine [benutzerdefinierte Rolle](microsoft-teams-rooms-premium-rbac.md#built-in-roles).




|Feature|Berechtigung|**MMR-Admin**|**Websiteleiter**|**Site Tech**|**Primäre Administratoren**|
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

> [!Note]
> Ein Benutzer, der als primärer Administrator für Kunde A zugewiesen ist, verfügt nur für diesen Kunden über vollständige Berechtigungen im TRM-Dienst. Die Berechtigungen des Benutzers in Kunde A haben keinen Einfluss auf andere Kunden.

## <a name="security"></a>Sicherheit

Endkunden behalten die Kontrolle über den Zugriff auf ihre Daten und können einen Partner oder bestimmte Rollen jederzeit vollständig entfernen.

Mit der Funktion für delegierten Zugriff erhält ein Partner außerhalb des TRM-Dienstportals keine weiteren Berechtigungen. Wenn Sie beispielsweise dieses Feature verwenden, um einen Partner zum Verwalten von Räumen im TRM-Dienst einzuladen, werden AAD oder dem Teams Admin Center oder einem anderen Microsoft-Produkt keine Berechtigungen erteilt. Darüber hinaus haben Partner keinen Zugriff darauf, Räume anzuzeigen oder zu ändern, die nicht im Einladungsbereich definiert sind.

Sobald der Partner – die Kundenbeziehung – wie in "Onboarding-Kunden" dieses Dokuments beschrieben – eingerichtet wurde, kann der Partner Raumdaten im TRM-Dienst anzeigen. Dies schließt alle Daten ein, die im TRM-Dienst vorhanden sind, aber von anderen Microsoft-Produkten abgeleitet sind. Beispielsweise werden Anrufqualitätsberichte im TRM-Portal von Teams-Anrufqualitätsdaten abgeleitet.

Die Daten befinden sich im Mandanten des Kunden und werden nicht in den Mandanten des Partners kopiert. 

Das MTM-Portal verwendet die AAD-Authentifizierung, um die Anmeldeinformationen des Partners zu überprüfen. Es ist wichtig zu beachten, dass die Authentifizierungsrichtlinien des Kunden zu diesem Zeitpunkt nicht für den Partner gelten. Wenn der Kunde beispielsweise über eine mehrstufige Authentifizierungsrichtlinie verfügt, wird diese nicht in den Partner übersetzt.

Der Kunde kann Überwachungsprotokolle für den TRM-Dienst abrufen, der Partneraktivitäten umfasst. Siehe [Überwachungsprotokollierung im Teams-Räume verwalteten Dienst](multi-tenant-auditing.md).

> [!Note]
> AAD-Überwachung und O365-Überwachung erfassen keine Protokolle aus dem TRM-Portal.

## <a name="navigating-the-mtm-portal"></a>Navigieren im MTM-Portal

Das MTM-Portal verfügt über zwei interaktive Modelle zum Navigieren zwischen Kundendaten:

- Aggregierte Ansichten, in denen Daten von allen Ihren Kunden in einer einzigen Liste konsolidiert und gefiltert werden können.

  > [!Note]
  > Diese Ansicht wird nur auf der Seite **"Vorfälle** " unterstützt, wenn die **Ansicht "Alle Tickets aktivieren"** aktiviert ist.
  >
  > ![Abbildung 1](../media/multi-tenant-management-partner-001.png)

 - Mandantenwechsel, bei dem nur Daten aus dem in der Dropdownliste ausgewählten **Kunden** angezeigt werden.
