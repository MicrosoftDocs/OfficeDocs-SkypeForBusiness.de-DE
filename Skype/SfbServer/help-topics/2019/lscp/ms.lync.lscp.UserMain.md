---
title: Systemsteuerung – aktualisierte Benutzersuche
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
  - ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
f1.keywords:
  - CSH
ms.localizationpriority: medium
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
ROBOTS: 'NOINDEX, NOFOLLOW'
description: 'Sie können die Ergebnisse einer Suchabfrage verwenden, um Benutzer für Skype for Business Server zu konfigurieren. Sie können anhand des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der SIP-Adresse oder des Anschluss-URIs (Uniform Resource Identifier) nach Benutzern suchen. Sie können auch über die Lync Server-Systemsteuerung oder das Snap-In "Active Directory-Benutzer und -Computer" nach Benutzern suchen.'
---

# <a name="control-panel---updated-user-search"></a>Systemsteuerung – aktualisiert: Benutzersuche

Sie können die Ergebnisse einer Suchabfrage verwenden, um Benutzer für Skype for Business Server zu konfigurieren. Sie können anhand des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der SIP-Adresse oder des Anschluss-URIs (Uniform Resource Identifier) nach Benutzern suchen. Sie können auch über die Lync Server-Systemsteuerung oder das Snap-In "Active Directory-Benutzer und -Computer" nach Benutzern suchen.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Sie können die folgenden Aufgaben auf der Systemsteuerungsseite der **Benutzersuche** ausführen:

- [Nach Benutzern suchen](/previous-versions/office/lync-server-2013/lync-server-2013-search-for-lync-server-users)

- [Aktivieren oder Deaktivieren von Benutzern](/previous-versions/office/lync-server-2013/lync-server-2013-disable-or-re-enable-user-account-for-lync-server)

- [Verschieben von Benutzern](ms.lync.lscp.UserMove.md)

- [Verschieben aller Benutzer](ms.lync.lscp.UserMoveAll.md)

- [Zuweisen von Richtlinien zu Benutzern](/previous-versions/office/lync-server-2013/lync-server-2013-assigning-per-user-policies)

- [Aktivieren von Benutzern für Enterprise-VoIP in Skype for Business Server](../../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [Konfigurieren des Partnerverbunds, des Remotebenutzerzugriffs und der Verbindung mit öffentlichen Chatdiensten für Benutzer](/previous-versions/office/lync-server-2013/lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user)

- [Konfigurieren der Telefonie für Benutzer](/previous-versions/office/lync-server-2013/lync-server-2013-configure-telephony-for-a-user)



## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite **Benutzersuche** beschrieben.

### <a name="user-search"></a>Benutzersuche

- **Suche** Suchen Sie nach Benutzern nach dem ersten Teil des Anzeigenamens, Vornamens, Nachnamens, SAM-Kontonamens, SIP-Adresse oder Zeilen-URI des Benutzerkontos.

- **LDAP-Suche** Suchen Sie nach Benutzern, indem Sie einen LDAP-Ausdruck eingeben.

- **Feld "Benutzer durchsuchen"** Geben Sie die Benutzerdaten oder den LDAP-Ausdruck ein, für den sie verwendet werden sollen.

- **Finden** Klicken Sie hier, um die Benutzer anzuzeigen, die den von Ihnen im **Suchbenutzer und -** feld eingegebenen Suchwerten entsprechen.

- **Abfrage öffnen** Klicken Sie, um eine gespeicherte Suchabfrage zu öffnen.

- **Abfrage speichern** Klicken Sie, um eine Suchabfrage zu speichern.

- **+ Filter hinzufügen** Klicken Sie, um zusätzliche Suchkriterien hinzuzufügen.

- **Suchfilterfelder** Wählen Sie das Feld aus, nach dem Sie Suchergebnisse filtern möchten, wählen Sie einen Operator für die Abfrage aus, und geben Sie dann die Zeichenfolge ein, nach der Sie suchen möchten.

- **Maximal anzuzeigende Benutzer** Geben Sie die Anzahl der Anzuzeigenden Suchergebnisse ein, oder verwenden Sie die Pfeile nach oben und unten, um die Zahl anzugeben.

Fügen Sie je nach Bedarf weiteren Beschreibungstext hinzu.

### <a name="search-results-menus"></a>Suchergebnismenüs

- **Aktivieren von Benutzern** Klicken Sie hier, um das Dialogfeld ["Benutzer: Neuer Lync Server-Benutzer](ms.lync.lscp.UserNew.md)" zu öffnen, in dem Sie Skype for Business Server einen neuen Benutzer hinzufügen können.

    Klicken Sie zum Hinzufügen eines neuen Kontakts auf den Pfeil nach unten, und wählen Sie dann die Option **Kontakte aktivieren**, um das Dialogfeld [Users: New Contact Objects](ms.lync.lscp.UserNewContact.md) zu öffnen.

- **Bearbeiten** Klicken Sie auf **"Bearbeiten** " und dann auf **"Details anzeigen** ", um die Details des ausgewählten Benutzers anzuzeigen, oder klicken Sie auf **"Alle Suchergebnisse auswählen** ", um alle Benutzer auszuwählen, die in der Ergebnistabelle angezeigt werden.

- **Aktion** Klicken Sie auf **"Aktion**", und wählen Sie dann die Aktion aus, die Sie für die ausgewählten Benutzer in den Suchergebnissen ausführen möchten. Die folgenden Aktionen sind verfügbar:

  - **Erneutes Aktivieren für Lync Server** Aktiviert das ausgewählte Benutzerkonto, nachdem es vorübergehend deaktiviert wurde.

  - **Vorübergehende Deaktivierung für Lync Server** Deaktiviert das Benutzerkonto in Skype for Business Server, bis Sie es erneut aktivieren, ohne das Benutzerkonto zu entfernen.

  - **Zuweisen von Richtlinien** Öffnet das Dialogfeld ["Benutzer: Richtlinien zuweisen](ms.lync.lscp.UserAssignPolicy.md) ", in dem Sie die dem Benutzer zugewiesenen Richtlinien konfigurieren können.

  - **Anzeigen des PIN-Status** Öffnet das Dialogfeld ["Benutzer: PIN-Status anzeigen](ms.lync.lscp.UserViewPin.md) ", in dem die PIN-Daten für den ausgewählten Benutzer angezeigt werden.

  - **Pin festlegen** Öffnet das Dialogfeld [PIN festlegen](ms.lync.lscp.UserSetPin.md) , in dem Sie die PIN für den ausgewählten Benutzer festlegen können.

  - **PIN sperren** Sperrt die PIN für den Benutzer.

  - **PIN entsperren** Entfernt die Sperre für die PIN des Benutzers.

  - **Entfernen aus Lync Server** Entfernt das Benutzerkonto aus Skype for Business Server. Der Benutzer wird dabei nicht aus Active Directory entfernt.

  - **Entfernen des Benutzerzertifikats** Entfernt alle Zertifikate, die dem Benutzer erteilt wurden.

  - **Verschieben ausgewählter Benutzer in den Pool** Öffnet das Dialogfeld ["Benutzer verschieben](ms.lync.lscp.UserMove.md) ", in dem Sie einen Pool auswählen können, in den der ausgewählte Benutzer verschoben werden soll.

  - **Verschieben aller Benutzer in den Pool** Öffnet das Dialogfeld ["Benutzer verschieben](ms.lync.lscp.UserMove.md) ", in dem Sie einen Pool auswählen können, in den alle ausgewählten Benutzer verschoben werden sollen.