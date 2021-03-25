---
title: Systemsteuerung – aktualisierte Benutzersuche
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
ROBOTS: NOINDEX, NOFOLLOW
description: Sie können die Ergebnisse einer Suchabfrage verwenden, um Benutzer für Skype for Business Server zu konfigurieren. Sie können anhand des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der SIP-Adresse oder des Anschluss-URIs (Uniform Resource Identifier) nach Benutzern suchen. Sie können auch mithilfe der Lync Server-Systemsteuerung oder des Active Directory-Snap-Ins Benutzer und Computer nach Benutzern suchen.
ms.openlocfilehash: ff98ed04ce4d411c118e9b0b497a2118ba38e17e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120094"
---
# <a name="control-panel---updated-user-search"></a>Systemsteuerung – aktualisiert: Benutzersuche

Sie können die Ergebnisse einer Suchabfrage verwenden, um Benutzer für Skype for Business Server zu konfigurieren. Sie können anhand des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der SIP-Adresse oder des Anschluss-URIs (Uniform Resource Identifier) nach Benutzern suchen. Sie können auch mithilfe der Lync Server-Systemsteuerung oder des Active Directory-Snap-Ins Benutzer und Computer nach Benutzern suchen.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Sie können die folgenden Aufgaben auf der Seite **Benutzersuchsteuerung** ausführen:

- [Suchen nach Benutzern](/previous-versions/office/lync-server-2013/lync-server-2013-search-for-lync-server-users)

- [Aktivieren oder Deaktivieren von Benutzern](/previous-versions/office/lync-server-2013/lync-server-2013-disable-or-re-enable-user-account-for-lync-server)

- [Verschieben von Benutzern](ms.lync.lscp.UserMove.md)

- [Verschieben aller Benutzer](ms.lync.lscp.UserMoveAll.md)

- [Zuweisen von Richtlinien zu Benutzern](/previous-versions/office/lync-server-2013/lync-server-2013-assigning-per-user-policies)

- [Aktivieren von Benutzern für Enterprise-VoIP in Skype for Business Server](../../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [Konfigurieren der Verbund-, Remotebenutzerzugriffs- und Öffentlichen Im-Konnektivität für Benutzer](/previous-versions/office/lync-server-2013/lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user)

- [Konfigurieren der Telefonie für Benutzer](/previous-versions/office/lync-server-2013/lync-server-2013-configure-telephony-for-a-user)



## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite **Benutzersuche** beschrieben.

### <a name="user-search"></a>Benutzersuche

- **Suche** Suchen Sie nach Benutzern nach dem ersten Teil des Anzeigenamens, Vornamens, Nachnamens, SAM-Kontonamens, SIP-Adresse oder Zeilen-URI des Benutzerkontos.

- **LDAP-Suche** Suchen Sie nach Benutzern, indem Sie einen LDAP-Ausdruck eingeben.

- **Suchbenutzerfeld** Geben Sie die Benutzerdaten oder den LDAP-Ausdruck ein, nach dem Sie eine Verbindung erstellen möchten.

- **Suchen** Klicken Sie hier, um die Benutzer anzeigen zu können, die den Suchwerten entsprechen, die Sie im Feld Benutzer **suchen** und eingegeben haben.

- **Abfrage öffnen** Klicken Sie auf, um eine gespeicherte Suchabfrage zu öffnen.

- **Abfrage speichern** Klicken Sie hier, um eine Suchabfrage zu speichern.

- **+ Filter hinzufügen** Klicken Sie hier, um weitere Suchkriterien hinzuzufügen.

- **Suchfilterfelder** Wählen Sie das Feld aus, nach dem Sie Suchergebnisse filtern möchten, wählen Sie einen Operator für die Abfrage aus, und geben Sie dann die Zeichenfolge ein, nach der Gesucht werden soll.

- **Maximale Anzahl angezeigter Benutzer** Geben Sie die Anzahl der Suchergebnisse ein, die Sie anzeigen möchten, oder verwenden Sie die Pfeile nach oben und unten, um die Zahl anzugeben.

Fügen Sie je nach Bedarf weiteren Beschreibungstext hinzu.

### <a name="search-results-menus"></a>Suchergebnismenüs

- **Aktivieren von Benutzern** Klicken Sie hier, um das Dialogfeld [Benutzer: Neuer Lync Server-Benutzer](ms.lync.lscp.UserNew.md) zu öffnen, in dem Sie Skype for Business Server einen neuen Benutzer hinzufügen können.

    Klicken Sie zum Hinzufügen eines neuen Kontakts auf den Pfeil nach unten, und wählen Sie dann die Option **Kontakte aktivieren**, um das Dialogfeld [Users: New Contact Objects](ms.lync.lscp.UserNewContact.md) zu öffnen.

- **Bearbeiten** Klicken **Sie auf**  Bearbeiten, und klicken Sie dann auf  Details anzeigen, um die Details des ausgewählten Benutzers anzuzeigen, oder klicken Sie auf Alle Suchergebnisse auswählen, um alle In der Ergebnistabelle angezeigten Benutzer auszuwählen.

- **Aktion** Klicken **Sie auf** Aktion, und wählen Sie dann die Aktion aus, die Sie für die ausgewählten Benutzer in den Suchergebnissen ausführen möchten. Die folgenden Aktionen sind verfügbar:

  - **Erneutes Aktivieren für Lync Server** Aktiviert das ausgewählte Benutzerkonto, nachdem es vorübergehend deaktiviert wurde.

  - **Vorübergehende Deaktivierung für Lync Server** Deaktiviert das Benutzerkonto in Skype for Business Server, bis Sie es erneut aktivieren, ohne das Benutzerkonto zu entfernen.

  - **Zuweisen von Richtlinien** Öffnet das [Dialogfeld Benutzer: Richtlinien zuweisen,](ms.lync.lscp.UserAssignPolicy.md) in dem Sie die dem Benutzer zugewiesenen Richtlinien konfigurieren können.

  - **Anzeigen des PIN-Status** Öffnet das [Dialogfeld Benutzer: PIN-Status](ms.lync.lscp.UserViewPin.md) anzeigen, in dem die PIN-Daten für den ausgewählten Benutzer angezeigt werden.

  - **Festlegen der PIN** Öffnet das [Dialogfeld PIN festlegen,](ms.lync.lscp.UserSetPin.md) in dem Sie die PIN für den ausgewählten Benutzer festlegen können.

  - **Sperr-PIN** Sperrt die PIN für den Benutzer.

  - **PIN entsperren** Entfernt die Sperre für die PIN des Benutzers.

  - **Entfernen von Lync Server** Entfernt das Benutzerkonto aus Skype for Business Server. Der Benutzer wird dabei nicht aus Active Directory entfernt.

  - **Entfernen von Benutzerzertifikaten** Entfernt alle Zertifikate, die dem Benutzer gewährt wurden.

  - **Verschieben ausgewählter Benutzer in einen Pool** Öffnet das [Dialogfeld Benutzer verschieben,](ms.lync.lscp.UserMove.md) in dem Sie einen Pool zum Verschieben des ausgewählten Benutzers auswählen können.

  - **Verschieben aller Benutzer in den Pool** Öffnet das [Dialogfeld Benutzer verschieben,](ms.lync.lscp.UserMove.md) in dem Sie einen Pool zum Verschieben aller ausgewählten Benutzer auswählen können.