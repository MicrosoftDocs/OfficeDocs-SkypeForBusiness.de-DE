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
description: Sie können die Ergebnisse einer Suchabfrage verwenden, um Benutzer für Skype for Business Server zu konfigurieren. Sie können anhand des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der SIP-Adresse oder des Anschluss-URIs (Uniform Resource Identifier) nach Benutzern suchen. Sie können auch mithilfe der Lync Server-Systemsteuerung oder des Active Directory-Snap-Ins "Benutzer und Computer" nach Benutzern suchen.
ms.openlocfilehash: 699f0a4eeb07eb1ac056cdf4777853b163fdb1c0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800365"
---
# <a name="control-panel---updated-user-search"></a>Systemsteuerung – aktualisiert: Benutzersuche

Sie können die Ergebnisse einer Suchabfrage verwenden, um Benutzer für Skype for Business Server zu konfigurieren. Sie können anhand des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der SIP-Adresse oder des Anschluss-URIs (Uniform Resource Identifier) nach Benutzern suchen. Sie können auch mithilfe der Lync Server-Systemsteuerung oder des Active Directory-Snap-Ins "Benutzer und Computer" nach Benutzern suchen.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite "Systemsteuerung der **Benutzersuche"** können Sie die folgenden Aufgaben ausführen:

- [Suchen nach Lync Server 2010-Benutzern](https://technet.microsoft.com/library/3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5.aspx)

- [Aktivieren oder Deaktivieren von Benutzern für Lync Server 2010](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)

- [Verschieben von Benutzern](move-user.md)

- [Verschieben aller Benutzer](move-all-users.md)

- [Zuweisen von Richtlinien zu Benutzern](https://technet.microsoft.com/library/a4ed0120-d9e5-4eb2-acfd-8de2cb503652.aspx)

- [Aktivieren von Benutzern für Enterprise-VoIP in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [Konfigurieren des Verbunds, des Remotebenutzerzugriffs und der Verbindung mit öffentlichen Verbindungen für Benutzer](https://technet.microsoft.com/library/736fcaad-9f95-4896-b767-e199d86a00a4.aspx)

- [Konfigurieren der Telefonie für Benutzer](https://technet.microsoft.com/library/4546432e-c839-4517-a2c5-bc0d4d8c6a03.aspx)

Details zu den verschiedenen Verfahren, die Sie mithilfe der Skype for Business Server-Systemsteuerung ausführen können, finden Sie unter ["Verwalten von Skype for Business Server 2015".](../../manage/manage.md)

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite **Benutzersuche** beschrieben.

### <a name="user-search"></a>Benutzersuche

- **Suche** Suchen Sie nach Benutzern nach dem ersten Teil des Anzeigenamens, Vornamens, Nachnamens, SAM-Kontonamens, der SIP-Adresse oder des Zeilen-URI des Benutzerkontos.

- **LDAP Search** Suchen Sie nach Benutzern, indem Sie einen LDAP-Ausdruck eingeben.

- **Feld "Benutzer durchsuchen"** Geben Sie die Benutzerdaten oder den LDAP-Ausdruck ein, nach dem Sie eine Suche erstellen möchten.

- **Suchen** Klicken Sie auf diese Schaltfläche, um die Benutzer anzeigen, die mit den Suchwerten übereinstimmen, die Sie im Feld **"Benutzer** suchen" und im Feld "Suchen" eingegeben haben.

- **Abfrage öffnen** Klicken Sie, um eine gespeicherte Suchabfrage zu öffnen.

- **Abfrage speichern** Klicken Sie auf diese Schaltfläche, um eine Suchabfrage zu speichern.

- **+ Filter hinzufügen** Klicken Sie auf diese Schaltfläche, um weitere Suchkriterien hinzuzufügen.

- **Suchfilterfelder** Wählen Sie das Feld aus, nach dem Sie Suchergebnisse filtern möchten, wählen Sie einen Operator für die Abfrage aus, und geben Sie dann die Zeichenfolge ein, nach der Sie suchen möchten.

- **Maximal zu anzeigede Benutzer** Geben Sie die Anzahl der Suchergebnisse ein, die angezeigt werden sollen, oder verwenden Sie die Nach-oben- und Abwärtspfeile, um die Zahl anzugeben.

Fügen Sie je nach Bedarf weiteren Beschreibungstext hinzu.

### <a name="search-results-menus"></a>Suchergebnismenüs

- **Aktivieren von Benutzern** Klicken Sie, um das Dialogfeld ["Benutzer: Neuer Lync Server-Benutzer"](users-new-lync-server-user.md) zu öffnen, in dem Sie Skype for Business Server einen neuen Benutzer hinzufügen können.

    Klicken Sie zum Hinzufügen eines neuen Kontakts auf den Pfeil nach unten, und wählen Sie dann die Option **Kontakte aktivieren**, um das Dialogfeld [Users: New Contact Objects](users-new-contact-objects.md) zu öffnen.

- **Bearbeiten** Klicken **Sie auf**  "Bearbeiten" und dann auf "Details  anzeigen", um die Details des ausgewählten Benutzers anzuzeigen, oder klicken Sie auf "Alle Suchergebnisse auswählen", um alle in der Ergebnistabelle angezeigten Benutzer auszuwählen.

- **Aktion** Klicken **Sie auf**"Aktion", und wählen Sie dann die Aktion aus, die Sie für die ausgewählten Benutzer in den Suchergebnissen ausführen möchten. Die folgenden Aktionen sind verfügbar:

  - **Erneutes Aktivieren für Lync Server** Aktiviert das ausgewählte Benutzerkonto, nachdem es vorübergehend deaktiviert wurde.

  - **Vorübergehende Deaktivierung für Lync Server** Deaktiviert das Benutzerkonto in Skype for Business Server, bis Sie es erneut aktivieren, ohne das Benutzerkonto zu entfernen.

  - **Zuweisen von Richtlinien** Öffnet das [Dialogfeld "Benutzer:](users-assign-policies.md) Richtlinien zuweisen", in dem Sie die dem Benutzer zugewiesenen Richtlinien konfigurieren können.

  - **Anzeigen des PIN-Status** Öffnet das [Dialogfeld "Benutzer: PIN-Status](users-view-pin-status.md) anzeigen", in dem die PIN-Daten für den ausgewählten Benutzer angezeigt werden.

  - **Festlegen der PIN** Öffnet das [Dialogfeld "PIN festlegen",](set-pin.md) in dem Sie die PIN für den ausgewählten Benutzer festlegen können.

  - **PIN sperren** Sperrt die PIN für den Benutzer.

  - **PIN entsperren** Entfernt die Sperre für die PIN des Benutzers.

  - **Entfernen aus Lync Server** Entfernt das Benutzerkonto aus Skype for Business Server. Der Benutzer wird dabei nicht aus Active Directory entfernt.

  - **Entfernen eines Benutzerzertifikats** Entfernt alle Zertifikate, die dem Benutzer erteilt wurden.

  - **Verschieben ausgewählter Benutzer in den Pool** Öffnet das [Dialogfeld "Benutzer verschieben",](move-user.md) in dem Sie einen Pool zum Verschieben des ausgewählten Benutzers auswählen können.

  - **Verschieben aller Benutzer in den Pool** Öffnet das [Dialogfeld "Benutzer verschieben",](move-user.md) in dem Sie einen Pool zum Verschieben aller ausgewählten Benutzer auswählen können.


