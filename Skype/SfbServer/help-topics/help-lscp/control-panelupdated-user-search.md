---
title: Systemsteuerung – aktualisierte Benutzersuche
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 5/21/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
description: Sie können die Ergebnisse einer Suchabfrage verwenden, um Benutzer für Skype for Business Server zu konfigurieren. Sie können anhand des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der SIP-Adresse oder des Anschluss-URIs (Uniform Resource Identifier) nach Benutzern suchen. Sie können auch mithilfe der Lync Server-Systemsteuerung oder des Active Directory-Snap-Ins Benutzer und Computer nach Benutzern suchen.
ms.openlocfilehash: 117f1c6a5a697cb1cf9e8e1f5c6cbf8363c517bf
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119934"
---
# <a name="control-panel---updated-user-search"></a>Systemsteuerung – aktualisiert: Benutzersuche

Sie können die Ergebnisse einer Suchabfrage verwenden, um Benutzer für Skype for Business Server zu konfigurieren. Sie können anhand des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der SIP-Adresse oder des Anschluss-URIs (Uniform Resource Identifier) nach Benutzern suchen. Sie können auch mithilfe der Lync Server-Systemsteuerung oder des Active Directory-Snap-Ins Benutzer und Computer nach Benutzern suchen.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Sie können die folgenden Aufgaben auf der Seite **Benutzersuchsteuerung** ausführen:

- [Suchen nach Lync Server 2010-Benutzern](/previous-versions/office/lync-server-2013/lync-server-2013-search-for-lync-server-users)

- [Aktivieren oder Deaktivieren von Benutzern für Lync Server 2010](/previous-versions/office/lync-server-2013/lync-server-2013-disable-or-re-enable-user-account-for-lync-server)

- [Verschieben von Benutzern](move-user.md)

- [Verschieben aller Benutzer](move-all-users.md)

- [Zuweisen von Richtlinien zu Benutzern](/previous-versions/office/lync-server-2013/lync-server-2013-assigning-per-user-policies)

- [Aktivieren von Benutzern für Enterprise-VoIP in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [Konfigurieren der Verbund-, Remotebenutzerzugriffs- und Öffentlichen Im-Konnektivität für Benutzer](/previous-versions/office/lync-server-2013/lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user)

- [Konfigurieren der Telefonie für Benutzer](/previous-versions/office/lync-server-2013/lync-server-2013-configure-telephony-for-a-user)

Weitere Informationen zu den verschiedenen Verfahren, die Sie mithilfe der Skype for Business Server-Systemsteuerung ausführen können, finden Sie unter [Manage Skype for Business Server 2015](../../manage/manage.md).

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

- **Aktivieren von Benutzern** Klicken Sie hier, um das Dialogfeld [Benutzer: Neuer Lync Server-Benutzer](users-new-lync-server-user.md) zu öffnen, in dem Sie Skype for Business Server einen neuen Benutzer hinzufügen können.

    Klicken Sie zum Hinzufügen eines neuen Kontakts auf den Pfeil nach unten, und wählen Sie dann die Option **Kontakte aktivieren**, um das Dialogfeld [Users: New Contact Objects](users-new-contact-objects.md) zu öffnen.

- **Bearbeiten** Klicken **Sie auf**  Bearbeiten, und klicken Sie dann auf  Details anzeigen, um die Details des ausgewählten Benutzers anzuzeigen, oder klicken Sie auf Alle Suchergebnisse auswählen, um alle In der Ergebnistabelle angezeigten Benutzer auszuwählen.

- **Aktion** Klicken **Sie auf** Aktion, und wählen Sie dann die Aktion aus, die Sie für die ausgewählten Benutzer in den Suchergebnissen ausführen möchten. Die folgenden Aktionen sind verfügbar:

  - **Erneutes Aktivieren für Lync Server** Aktiviert das ausgewählte Benutzerkonto, nachdem es vorübergehend deaktiviert wurde.

  - **Vorübergehende Deaktivierung für Lync Server** Deaktiviert das Benutzerkonto in Skype for Business Server, bis Sie es erneut aktivieren, ohne das Benutzerkonto zu entfernen.

  - **Zuweisen von Richtlinien** Öffnet das [Dialogfeld Benutzer: Richtlinien zuweisen,](users-assign-policies.md) in dem Sie die dem Benutzer zugewiesenen Richtlinien konfigurieren können.

  - **Anzeigen des PIN-Status** Öffnet das [Dialogfeld Benutzer: PIN-Status](users-view-pin-status.md) anzeigen, in dem die PIN-Daten für den ausgewählten Benutzer angezeigt werden.

  - **Festlegen der PIN** Öffnet das [Dialogfeld PIN festlegen,](set-pin.md) in dem Sie die PIN für den ausgewählten Benutzer festlegen können.

  - **Sperr-PIN** Sperrt die PIN für den Benutzer.

  - **PIN entsperren** Entfernt die Sperre für die PIN des Benutzers.

  - **Entfernen von Lync Server** Entfernt das Benutzerkonto aus Skype for Business Server. Der Benutzer wird dabei nicht aus Active Directory entfernt.

  - **Entfernen von Benutzerzertifikaten** Entfernt alle Zertifikate, die dem Benutzer gewährt wurden.

  - **Verschieben ausgewählter Benutzer in einen Pool** Öffnet das [Dialogfeld Benutzer verschieben,](move-user.md) in dem Sie einen Pool zum Verschieben des ausgewählten Benutzers auswählen können.

  - **Verschieben aller Benutzer in den Pool** Öffnet das [Dialogfeld Benutzer verschieben,](move-user.md) in dem Sie einen Pool zum Verschieben aller ausgewählten Benutzer auswählen können.