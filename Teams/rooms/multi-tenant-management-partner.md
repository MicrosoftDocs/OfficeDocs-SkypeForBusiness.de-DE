---
title: Kundenverwaltung mit mehreren Mandanten für Partner
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
description: Kundenverwaltung mit mehr Mandanten für Partner.
f1keywords: ''
ms.openlocfilehash: 5ce4493ef9a5e6c959bf10c600c2b9697129d9df
ms.sourcegitcommit: 4095a1d5e507ac5cb23ed17611c1fbd4b744b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/13/2021
ms.locfileid: "61420205"
---
# <a name="multi-tenant-customer-management-for-partners"></a>Kundenverwaltung mit mehreren Mandanten für Partner

Die Verwaltung mehrerer Mandanten (Multi-Tenant Management, MTM) im Dienst "Teams-Räume Managed (TRM)" hilft Partnerorganisationen bei der Verwaltung mehrerer Kunden an einem Ort mit ihren eigenen Domänenanmeldeinformationen. Partnerbenutzern werden nur Kundenräume sehen, die ihnen zugewiesen wurden, um sie zu verwalten. Es ist möglich, für jeden Kunden im MTM-Mandanten benutzerdefinierte Rollen anzuwenden, damit Partnerorganisationen die Berechtigungen für die Ressourcen des Kunden präzise steuern können. 

Auf das MTM-Portal kann über diesen Link zugegriffen [werden.](https://partner.rooms.microsoft.com/)

> [!Note] 
> Partnerorganisationen können ihre eigenen Räume nicht über das MTM-Portal verwalten. Diese Räume können im [TRM-Portal verwaltet werden.](https://portal.rooms.microsoft.com/) 

## <a name="pre-requisites-for-managing-your-customers-through-the-mtm-experience"></a>Voraussetzungen für die Verwaltung Ihrer Kunden über die MTM-Erfahrung

Um Zugriff auf das MTM-Portal zu erhalten, muss Ihre Organisation als Elite-Partner für den TRM-Dienst onboarded sein. Um ein Elite-Partner zu werden, wenden Sie sich askelite@microsoft.com.


## <a name="on-boarding-customers"></a>Onboarding-Kunden

Um Kunden über das TRM-MTM-Portal zu verwalten, muss über eine vom Kunden gesendete Einladung eine Beziehung zwischen dem Mandanten der Partnerorganisation und dem Kunden eingerichtet werden. 

### <a name="invitation-from-the-customer"></a>Einladung vom Kunden

Der Partner stellt die Benutzerprinziplnamen (User Principle Names, UPNs) der Benutzer zur Verfügung, die dem Kunden primäre Administratoren zugewiesen werden sollen. Nur die in der Einladung identifizierten Benutzer können die Einladung sehen und annehmen, wenn sie sich beim TRM-MTM-Portal anmelden. 

> [!Note]
> Selbst wenn Sie über erhöhte Berechtigungen wie globaler Administrator verfügen, wird die Einladung nur dann dann sehen, wenn Sie explizit hinzugefügt wurden. 

Details zur Kundeneinladung finden Sie unter [Verwaltung von mehreren Mandanten für Kunden.](multi-tenant-management-customer.md)

**So akzeptieren Sie eine ausstehende Einladung**

1. Melden Sie sich als einer der Benutzer in der Einladung beim TRM-MTM-Portal an.
1. Wechseln Sie **zu Kunden.**
1. Wählen Sie die Einladung mit dem Status "Ausstehend" aus.
1. Überprüfen Sie die Einladungsdetails.
1. Wählen Sie **Annehmen** aus, um die Beziehung zwischen Partner und Kunde zu erstellen.

   Wenn **Sie Verweigern** auswählen, wird die Einladung, die der Benutzer verweigert, gelöscht. Die Einladung steht für andere Benutzer, die noch nicht reagiert haben, weiterhin zur Verfügung.

   > [!Note]
   > Die Einladung ist eindeutig und für jeden Benutzer unabhängig. Der erste zu akzeptierende Benutzer richtet die Verknüpfung zwischen dem Partner- und Kunden-Mandanten ein. Es gibt keine dauerhafte Verknüpfung mit dem Benutzer, der den Link einhing. Nachfolgende Benutzer, die die Einladung annehmen, werden als primäre Administratoren hinzugefügt.

   > [!Note]
   > *Wenn ein Partnerbenutzer die Einladung versehentlich verweigert, ist es am besten, dass ein anderer Benutzer ihn einfach der Rolle "Partner" (oder einer anderen RBAC-Rolle) für den Kunden hinzunimmt.* 

Nachdem der Benutzer die Einladung akzeptiert hat, wird er automatisch als Primäradministrator für den Mandanten dieses Kunden hinzugefügt. 

Um die Konfiguration für diesen Mandanten zu überprüfen, wählen Sie den Kunden in der Liste **Kunden** aus.


## <a name="off-boarding-customers"></a>Offboarding-Kunden

Um einen Kunden aus der Liste "Kunden" zu entfernen, müssen Sie diesen aus der Liste "Kunden" entfernen.

**So entfernen Sie einen Kunden** 

1. Melden Sie sich beim TRM-MTM-Portal als Primäradministrator für den Kunden an, den Sie entfernen möchten.
1. Wechseln Sie **zu Kunden.**
1. Wählen Sie den Kunden aus, den Sie entfernen möchten.
1. Wählen Sie im Detailbereich des Kunden die Option **Kunden entfernen aus.**
1. Wählen **Sie in** der Bestätigungsaufforderung Löschen aus, um die Zuordnung zwischen Ihrem und dem Kunden-Mandanten zu beenden.


## <a name="managing-partner-roles"></a>Verwalten von Partnerrollen

Partnerrollen ermöglichen die Delegierung von Zuständigkeiten an zusätzliche Mitarbeiter. Das Konzept dieser Rollen ist das gleiche, das [unter](microsoft-teams-rooms-premium-rbac.md)Rollenbasierte Zugriffssteuerung beschrieben wird, aber im Kontext jedes Kunden. Außerdem ist es wichtig zu beachten, dass sich Partnerrollen von den Rollen des Kunden unterscheiden. Die Partnerrollen können vom Kunden gelöscht werden. 

Die Rolle **der** primären Administratoren ist die einzige integrierte Rolle für jeden integrierten Kunden und verfügt – im Kontext des Kunden – über fast alle Berechtigungen für den TRM-Dienst (siehe Tabelle 1). Rollenberechtigungen für Partner** reichen nur bis zu den vom Kunden festgelegten Räumen. Wenn der Kunde beispielsweise eine globale Organisation ist und dem Partner die Verwaltung aller US-Räume zu weist, kann der primäre Administrator berechtigungen nur für diese Räume verwalten und delegieren. Der Partner hat keine Sichtbarkeit für andere Räume, die der Kunde möglicherweise in anderen Ländern hat. 

> [!Important]
> Die Rolle "Primäre Administratoren" muss immer **mindestens einen Benutzer** haben.

**So verwalten Sie Benutzer in **der Partnerrolle** für einen Kunden**

1. Wechseln Sie **zu Einstellungen > Rollen.** 
1. Wählen Sie den Kunden aus der Dropdownliste aus, für den Sie die Partnerrolle bearbeiten möchten.
1. Wählen Sie **die integrierte Rolle** "Primäre Administratoren" aus der Liste aus.
1. Wählen Sie **Aufgaben aus.**
1. Wählen Sie in der Liste die **Option Eingeladene Administratoren aus.**
1. Wählen Sie **Mitglieder aus.**
1. Klicken Sie auf **Bearbeiten auswählen.** 
1. Suchen Sie in der Suchleiste nach dem Benutzer oder der Sicherheitsgruppe, den bzw. die Sie hinzufügen möchten.
1. Wählen Sie den Benutzer oder die Gruppe aus.
1. Klicken Sie auf **Speichern,** um die Änderungen zu bestätigen.

### <a name="managing-custom-partner-roles-for-a-customer"></a>Verwalten von benutzerdefinierten Partnerrollen für einen Kunden

Als Partner können Sie benutzerdefinierte Rollen erstellen, die Ihren betrieblichen Anforderungen entsprechen. So können Sie beispielsweise eine Helpdesk-Rolle erstellen, die nur über Berechtigungen für die Vorfallverwaltung verfügen sollte. 

**So verwalten Sie Rollen**

1. Wechseln Sie **zu Einstellungen > Rollen.** 
1. Wählen Sie den Kunden aus der Dropdownliste aus, für den Sie die Partnerrolle bearbeiten möchten.
1. Erstellen Sie eine [benutzerdefinierte Rolle.](microsoft-teams-rooms-premium-rbac.md#built-in-roles)




|Feature|Berechtigung|**MMR Admin**|**Websiteleiter**|**Site Tech**|**Primäre Administratoren**|
| :- | :- | :- | :- | :- | :- |
|Räume|Anzeigen| &#10004;|&#10004;|&#10004;|&#10004;|
||Ändern|&#10004;|&#10004;|&#10004;|&#10004;|
||Rücksetztaste|&#10004;||||
||Downloadschlüssel|&#10004;|&#10004;|&#10004;||
||Registrierung aufenrolln|&#10004;|&#10004;|&#10004;||
||Erstellen |&#10004;|&#10004;|||
|Gruppenverwaltung|Anzeigen|&#10004;|&#10004;||&#10004;|
||Ändern|&#10004;|&#10004;|||
||Erstellen |&#10004;|&#10004;|||
|Verwaltung von Update-Ringen|Anzeigen|&#10004;|&#10004;||&#10004;|
||Ändern|&#10004;|&#10004;||&#10004;|
|Berichte|Anzeigen|&#10004;|&#10004;||&#10004;|
||Kundenvorfall erstellen|&#10004;|&#10004;|&#10004;|&#10004;|
|Ticketsverwaltung|Anzeigen|&#10004;|&#10004;|&#10004;|&#10004;|
||Aktualisieren|&#10004;|&#10004;|&#10004;|&#10004;|
|MMR Einstellungen|Anzeigen|&#10004;||||
||Ändern|&#10004;||||
|Rollenverwaltung|Anzeigen |&#10004;|||&#10004;|
||Ändern|&#10004;|||&#10004;|

> [!Note]
> Ein Benutzer, der als Primäradministrator für Kunde A zugewiesen ist, verfügt nur für diesen Kunden über vollständige Berechtigungen im TRM-Dienst. Die Berechtigungen des Benutzers in Kunde A haben keinen Einfluss auf andere Kunden.

## <a name="security"></a>Sicherheit

Endbenutzer behalten die Kontrolle über den Zugriff auf ihre Daten und können jederzeit einen Partner oder bestimmte Rollen vollständig entfernen.

Mit dem Feature für delegierten Zugriff hat ein Partner keine weiteren Rechte außerhalb des TRM-Dienstportals. Wenn Sie dieses Feature beispielsweise verwenden, um einen Partner zum Verwalten von Räumen im TRM-Dienst einzu einladen, werden AAD oder dem Teams Admin Center oder einem anderen Microsoft-Produkt keine Berechtigungen erteilt. Darüber hinaus haben Partner keinen Zugriff auf das Anzeigen oder Ändern von Räumen, die nicht im Einladungsbereich definiert sind.

Sobald die Beziehung zwischen Partner und Kunde eingerichtet ist – wie im Abschnitt "Onboarding-Kunden" dieses Dokument beschrieben – kann der Partner Raumdaten im TRM-Dienst anzeigen. Dies schließt alle Im TRM-Dienst vorhandenen, aber von anderen Microsoft-Produkten abgeleiteten Daten ein. Die Berichte zur Anrufqualität im TRM-Portal werden beispielsweise von den Teams der Anrufqualität abgeleitet.

Die Daten befinden sich im Mandanten des Kunden und werden nicht in den Mandanten des Partners kopiert. 

Das MTM-Portal verwendet AAD Authentifizierung, um die Anmeldeinformationen des Partners zu überprüfen. Beachten Sie, dass die Authentifizierungsrichtlinien des Kunden derzeit nicht für den Partner gelten. Wenn der Kunde beispielsweise über eine Mehrstufige Authentifizierungsrichtlinie verfügt, wird diese nicht für den Partner übersetzt.

Der Kunde kann Überwachungsprotokolle für den TRM-Dienst pullen, der Partneraktivitäten umfasst. Weitere [Informationen finden Sie unter Überwachungsprotokollierung im Teams-Räume verwalteten Dienst.](multi-tenant-auditing.md)

> [!Note]
> AAD- und O365-Überwachung erfasst keine Protokolle aus dem TRM-Portal.

## <a name="navigating-the-mtm-portal"></a>Navigieren im MTM-Portal

Das MTM-Portal verfügt über zwei interaktive Modelle zum Navigieren zwischen Kundendaten:

- Aggregieren von Ansichten, in denen Daten aller Kunden in einer einzelnen Liste konsolidiert und gefiltert werden können.

  > [!Note]
  > Diese Ansicht wird auf der Seite **"Vorfälle" nur** unterstützt, wenn die Option **Alle** Tickets aktivieren aktiviert ist.

  ![Abbildung 1](../media/multi-tenant-management-partner-001.png)

 - Mandantenumschaltung, bei der nur Daten **des** in der Dropdownliste ausgewählten Kunden angezeigt werden.
