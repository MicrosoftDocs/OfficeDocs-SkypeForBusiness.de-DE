---
title: Systemsteuerung – aktualisierte Benutzersuche
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
ROBOTS: NOINDEX, NOFOLLOW
description: Sie können die Ergebnisse einer Suchabfrage verwenden, um Benutzer für Skype for Business Server zu konfigurieren. Sie können anhand des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der SIP-Adresse oder des Anschluss-URI (Uniform Resource Identifier) nach Benutzern suchen. Ferner können Sie Benutzer über die Lync Server-Systemsteuerung oder das Snap-In „Active Directory-Benutzer und -Computer“ suchen.
ms.openlocfilehash: 6e966e6a58e221c6173842de7c2b25682f42caf1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281638"
---
# <a name="control-panel---updated-user-search"></a>Systemsteuerung – aktualisiert: Benutzersuche

Sie können die Ergebnisse einer Suchabfrage verwenden, um Benutzer für Skype for Business Server zu konfigurieren. Sie können anhand des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der SIP-Adresse oder des Anschluss-URI (Uniform Resource Identifier) nach Benutzern suchen. Ferner können Sie Benutzer über die Lync Server-Systemsteuerung oder das Snap-In „Active Directory-Benutzer und -Computer“ suchen.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Systemsteuerungsseite **Benutzersuche** können Sie die folgenden Aufgaben ausführen:

- [Nach Benutzern suchen](https://technet.microsoft.com/library/3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5.aspx)

- [Aktivieren oder Deaktivieren von Benutzern](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)

- [Verschieben von Benutzern](ms.lync.lscp.UserMove.md)

- [Verschieben aller Benutzer](ms.lync.lscp.UserMoveAll.md)

- [Assign Policies to Users](https://technet.microsoft.com/library/a4ed0120-d9e5-4eb2-acfd-8de2cb503652.aspx)

- [Aktivieren von Benutzern für Enterprise-VoIP in Skype for Business Server](../../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [Configure Federation, Remote User Access, and Public IM Connectivity for Users](https://technet.microsoft.com/library/736fcaad-9f95-4896-b767-e199d86a00a4.aspx)

- [Configure Telephony for Users](https://technet.microsoft.com/library/4546432e-c839-4517-a2c5-bc0d4d8c6a03.aspx)



## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite **Benutzersuche** beschrieben.

### <a name="user-search"></a>Benutzersuche

- **Suche nach** Suchen Sie nach Benutzern nach dem ersten Teil des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens, der SIP-Adresse oder des Leitungs-URIs des Benutzerkontos.

- **LDAP-Suche** Suchen Sie nach Benutzern, indem Sie einen LDAP-Ausdruck eingeben.

- **Feld "Benutzer suchen"** Geben Sie die Benutzerdaten oder LDAP-Ausdrücke ein, nach denen Sie suchen möchten.

- **Finden Sie** Klicken Sie auf diese Option, um die Benutzer anzuzeigen, die mit den Suchwerten übereinstimmen, die Sie in das Feld **Benutzer suchen** und eingegeben haben.

- **Abfrage öffnen** Klicken Sie, um eine gespeicherte Suchabfrage zu öffnen.

- **Abfrage speichern** Klicken Sie, um eine Suchabfrage zu speichern.

- **+ Filter hinzufügen** Klicken Sie hier, um weitere Suchkriterien hinzuzufügen.

- **Suchfilter Felder** Wählen Sie das Feld aus, in dem Sie die Suchergebnisse filtern möchten, wählen Sie einen Operator für die Abfrage aus, und geben Sie dann die Zeichenfolge ein, nach der Sie suchen möchten.

- **Maximal anzuzeigende Benutzer** Geben Sie die Anzahl der anzuzeigenden Suchergebnisse ein, oder verwenden Sie die nach-oben-und nach-unten-Taste, um die gewünschte Zahl anzugeben.

Fügen Sie je nach Bedarf weiteren Beschreibungstext hinzu.

### <a name="search-results-menus"></a>Suchergebnismenüs

- **Aktivieren von Benutzern** Klicken Sie hier, um das Dialogfeld [Benutzer: neuer lync Server-Benutzer](ms.lync.lscp.UserNew.md) zu öffnen, in dem Sie einen neuen Benutzer zu Skype for Business Server hinzufügen können.

    Klicken Sie auf den Pfeil nach unten und wählen Sie dann die Option **Kontakte aktivieren**, um das Dialogfeld [Users: New Contact Objects](ms.lync.lscp.UserNewContact.md) zu öffnen und einen neuen Kontakt hinzuzufügen.

- **Bearbeiten** von Klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen** , um die Details des ausgewählten Benutzers anzuzeigen, oder klicken Sie auf **alle Suchergebnisse auswählen** , um alle in der Tabelle Ergebnisse angezeigten Benutzer auszuwählen.

- **Aktion** Klicken Sie auf **Aktion**, und wählen Sie dann die Aktion aus, die Sie für die ausgewählten Benutzer in den Suchergebnissen ausführen möchten. Die folgenden Aktionen sind verfügbar:

  - **Erneutes Aktivieren für lync Server** Aktiviert das ausgewählte Benutzerkonto, nachdem es vorübergehend deaktiviert wurde.

  - **Vorübergehendes Deaktivieren für lync Server** Deaktiviert das Benutzerkonto in Skype for Business Server, bis Sie es wieder aktivieren, ohne das Benutzerkonto zu entfernen.

  - **Zuweisen von Richtlinien** Öffnet das Dialogfeld [Benutzer: Richtlinien zuweisen](ms.lync.lscp.UserAssignPolicy.md) , in dem Sie die Richtlinien konfigurieren können, die dem Benutzer zugewiesen sind.

  - **Pin-Status anzeigen** Öffnet das Dialogfeld " [Benutzer: Pin-Status anzeigen](ms.lync.lscp.UserViewPin.md) ", in dem die PIN-Daten für den ausgewählten Benutzer angezeigt werden.

  - **Pin setzen** Öffnet das Dialogfeld " [Pin setzen](ms.lync.lscp.UserSetPin.md) ", in dem Sie die PIN für den ausgewählten Benutzer einrichten können.

  - **PIN sperren** Sperrt die PIN für den Benutzer.

  - **PIN entsperren** Entfernt die Sperre für die PIN des Benutzers.

  - **Aus lync Server entfernen** Entfernt das Benutzerkonto aus Skype for Business Server. Der Benutzer wird dabei nicht aus Active Directory entfernt.

  - **Benutzerzertifikat entfernen** Entfernt alle dem Benutzer gewährten Zertifikate.

  - **Ausgewählte Benutzer in Pool verschieben** Öffnet das Dialogfeld " [Benutzer verschieben](ms.lync.lscp.UserMove.md) ", in dem Sie einen Pool auswählen können, in den der ausgewählte Benutzer verschoben werden soll.

  - **Verschieben aller Benutzer in den Pool** Öffnet das Dialogfeld " [Benutzer verschieben](ms.lync.lscp.UserMove.md) ", in dem Sie einen Pool auswählen können, in den Sie alle ausgewählten Benutzer verschieben möchten.


