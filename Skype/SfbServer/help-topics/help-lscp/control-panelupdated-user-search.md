---
title: Systemsteuerung - aktualisierte Benutzersuche
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 5/21/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
description: Die Ergebnisse einer Suchabfrage können Sie Benutzer für Skype für Business Server konfigurieren. Sie können anhand des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der SIP-Adresse oder des Anschluss-URI (Uniform Resource Identifier) nach Benutzern suchen. Ferner können Sie Benutzer über die Lync Server-Systemsteuerung oder das Snap-In „Active Directory-Benutzer und -Computer“ suchen.
ms.openlocfilehash: 5d94c468edeb8c982d901f1c396bfd49c8c88fb6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200828"
---
# <a name="control-panel---updated-user-search"></a>Systemsteuerung – aktualisiert: Benutzersuche

Die Ergebnisse einer Suchabfrage können Sie Benutzer für Skype für Business Server konfigurieren. Sie können anhand des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der SIP-Adresse oder des Anschluss-URI (Uniform Resource Identifier) nach Benutzern suchen. Ferner können Sie Benutzer über die Lync Server-Systemsteuerung oder das Snap-In „Active Directory-Benutzer und -Computer“ suchen.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Systemsteuerungsseite **Benutzersuche** können Sie die folgenden Aufgaben ausführen:

- [Search for Lync Server 2010 Users](https://technet.microsoft.com/library/3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5.aspx)

- [Enable or Disable Users for Lync Server 2010](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)

- [Verschieben von Benutzern](move-user.md)

- [Verschieben aller Benutzer](move-all-users.md)

- [Assign Policies to Users](https://technet.microsoft.com/library/a4ed0120-d9e5-4eb2-acfd-8de2cb503652.aspx)

- [Enable users for Enterprise Voice in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [Configure Federation, Remote User Access, and Public IM Connectivity for Users](https://technet.microsoft.com/library/736fcaad-9f95-4896-b767-e199d86a00a4.aspx)

- [Configure Telephony for Users](https://technet.microsoft.com/library/4546432e-c839-4517-a2c5-bc0d4d8c6a03.aspx)

Ausführliche Informationen zu den verschiedenen Verfahren, die Sie mithilfe der Skype für Business Server-Systemsteuerung ausführen können, finden Sie unter [Verwalten von Skype für Business Server 2015](../../manage/manage.md).

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite **Benutzersuche** beschrieben.

### <a name="user-search"></a>Benutzersuche

- **Suche** Suchen Sie nach den ersten Teil der Anzeigename, Vorname, Nachname, SAM-Kontoname, SIP-Adresse für Benutzer, oder Anschluss-URI des Benutzerkontos.

- **LDAP-Suche** Suchen von Benutzern, indem Sie einen LDAP-Ausdruck eingeben.

- **Suchfeld für Benutzer** Geben Sie die Benutzerdaten oder LDAP-Ausdruck für die Suche für die gewünschte.

- **Hier finden Sie** Klicken Sie auf diese Option, um die Benutzer anzuzeigen, die mit die Suchwerten übereinstimmen, den, die Sie im Feld **Benutzer suchen** und eingegeben haben.

- **Abfrage öffnen** Klicken Sie auf diese Option, um eine gespeicherte Suchabfrage zu öffnen.

- **Abfrage speichern** Klicken Sie auf diese Option, um eine Suchabfrage zu speichern.

- **+ Filter hinzufügen** Klicken Sie auf diese Option, um weitere Suchkriterien hinzuzufügen.

- **Suchfilterfelder** Wählen Sie das Feld, auf dem Sie die Suchergebnisse filtern, wählen einen Operator für die Abfrage, und geben Sie die Zeichenfolge für die Suche gewünschten möchten.

- **Maximale Benutzer anzeigen** Geben Sie die Anzahl der Suchergebnisse, den, die Sie anzeigen möchten, oder verwenden Sie die nach oben und nach-unten-Tasten aus, um die Anzahl anzugeben möchten.

Fügen Sie je nach Bedarf weiteren Beschreibungstext hinzu.

### <a name="search-results-menus"></a>Suchergebnismenüs

- **Aktivieren von Benutzern** Klicken Sie zum Öffnen der [Benutzer: neuer Lync Server-Benutzer](users-new-lync-server-user.md) Dialogfeld, in dem Sie einen neuen Benutzer zu Skype für Business Server hinzufügen können.

    Klicken Sie auf den Pfeil nach unten und wählen Sie dann die Option **Kontakte aktivieren**, um das Dialogfeld [Users: New Contact Objects](users-new-contact-objects.md) zu öffnen und einen neuen Kontakt hinzuzufügen.

- **Bearbeiten** Klicken Sie auf **Bearbeiten** , und klicken Sie dann auf **Details anzeigen** , um die Details zu den ausgewählten Benutzer anzuzeigen, oder klicken Sie auf **alle Suchergebnisse auswählen** , aktivieren Sie alle Benutzer in der Ergebnistabelle angezeigt.

- **Aktion** Klicken Sie auf **Aktion**, und wählen Sie dann die Aktion, den, die Sie für die ausgewählten Benutzer in den Suchergebnissen ausführen möchten. Die folgenden Aktionen sind verfügbar:

  - **Erneut für Lync Server aktivieren** Aktiviert das ausgewählte Benutzerkonto, nachdem es vorübergehend deaktiviert wurde.

  - **Deaktivieren Sie vorübergehend für Lync Server** Wird das Benutzerkonto in Skype für Business Server deaktiviert, bis Sie ihn wieder aktivieren, ohne Entfernen des Benutzerkontos.

  - **Zuweisen von Richtlinien** Öffnet die [Benutzer: Zuweisen von Richtlinien](users-assign-policies.md) Dialogfeld, in dem Sie die dem Benutzer zugewiesenen Richtlinien konfigurieren können.

  - **PIN-Status anzeigen** Öffnet die [Benutzer: View PIN Status](users-view-pin-status.md) Dialogfeld, in dem die PIN-Daten für den ausgewählten Benutzer angezeigt werden.

  - **PIN festlegen** Öffnet das Dialogfeld [Set PIN](set-pin.md) , in dem Sie die PIN für den ausgewählten Benutzer festlegen können.

  - **PIN Sperren** Sperrt die PIN für den Benutzer.

  - **PIN des Telefons** Entfernt die Sperre für die PIN des Benutzers an.

  - **Entfernen von Lync Server** Das Benutzerkonto entfernt von Skype für Business Server. Der Benutzer wird dabei nicht aus Active Directory entfernt.

  - **Benutzerzertifikat entfernen** Entfernt alle Zertifikate, die dem Benutzer gewährt wurden.

  - **Ausgewählte Benutzer in Pool verschieben** Öffnet das Dialogfeld [Benutzer verschieben](move-user.md) , in dem Sie einen Pool verschieben den ausgewählten Benutzer auswählen können.

  - **Alle Benutzer in Pool verschieben** Öffnet das Dialogfeld [Benutzer verschieben](move-user.md) , in dem Sie einen Pool an alle ausgewählten Benutzer verschieben auswählen können.


