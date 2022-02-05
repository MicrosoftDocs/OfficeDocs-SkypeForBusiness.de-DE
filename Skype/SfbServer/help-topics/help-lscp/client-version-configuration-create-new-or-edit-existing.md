---
title: Erstellen einer neuen oder Bearbeiten einer vorhandenen Clientversionskonfiguration
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
description: 'Clientversionskonfigurationseinstellungen werden verwendet, um die Clientversionskontrolle zu aktivieren oder zu deaktivieren. Die globale Clientversionskonfiguration wird mit Skype for Business Server installiert und wird verwendet, um die Clientversionskontrolle für die gesamte Serverbereitstellung zu aktivieren oder zu deaktivieren. Wenn die globale Konfiguration aktiviert ist, werden alle clientversionsrichtlinien, die Sie eingerichtet haben, wirksam, wenn Benutzer versuchen, sich anzumelden. Sie können die globale Clientversionskonfiguration deaktivieren, wenn keine Clientversionskontrolle erfolgen soll.'
---

# <a name="client-version-configuration-create-new-or-edit-existing"></a>Clientversionskonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Clientversionskonfiguration

Clientversionskonfigurationseinstellungen werden verwendet, um die Clientversionskontrolle zu aktivieren oder zu deaktivieren. Die globale Clientversionskonfiguration wird mit Skype for Business Server installiert und wird verwendet, um die Clientversionskontrolle für die gesamte Serverbereitstellung zu aktivieren oder zu deaktivieren. Wenn die globale Konfiguration aktiviert ist, werden alle clientversionsrichtlinien, die Sie eingerichtet haben, wirksam, wenn Benutzer versuchen, sich anzumelden. Sie können die globale Clientversionskonfiguration deaktivieren, wenn keine Clientversionskontrolle erfolgen soll.

Sie können auch standortspezifische Clientversionskonfigurationen erstellen, um die Clientversionskontrolle pro Standort aktivieren und deaktivieren zu können. Standortspezifische Konfigurationen haben Vorrang vor der globalen Konfiguration.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Neue Clientversionskonfiguration erstellen** oder **Clientversionskonfiguration bearbeiten** können Sie die folgenden Aufgaben ausführen:

- Hinzufügen oder Ändern des Namens der Clientversionskonfiguration

- Aktivieren und Deaktivieren der Clientversionskontrolle global oder für einen bestimmten Standort

- Hinzufügen oder Ändern der Standardaktion für die Clientversionskonfiguration

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.

- **Umfang** Gibt den Bereich (global oder Standort) der Clientversionskonfiguration an.

- **Namen** Sie können den Namen der Clientversionskonfiguration hinzufügen oder ändern.

- **Aktivieren der Versionskontrolle** Sie können die Clientversionskontrolle je nach Konfigurationsumfang global oder für den Standort aktivieren oder deaktivieren.

- **Standardaktion** Sie können die Standardaktion auswählen, die angewendet wird, wenn ein Benutzer versucht, sich mit einer Clientanwendung anzumelden, für die keine bestimmte Clientversionsrichtlinie vorhanden ist. Sie haben folgende Optionen:

  - **Ermöglichen** Ermöglicht dem Client die Anmeldung, wenn die Clientversion keinem Filter in der Liste der Clientversionsrichtlinien entspricht.

  - **Block** Verhindert, dass sich der Client anmeldet, wenn die Clientversion keinem Filter in der Liste der Clientversionsrichtlinien entspricht.

  - **Blockieren mit URL** Verhindert, dass sich der Client anmeldet, wenn die Clientversion keinem Filter in der Liste der Clientversionsrichtlinien entspricht, und enthält eine Fehlermeldung mit einer URL, unter der ein neuerer Client heruntergeladen werden kann.

  - **Zulassen mit URL** Ermöglicht dem Client die Anmeldung, wenn die Clientversion keinem Filter in der Liste der Clientversionsrichtlinien entspricht, und enthält eine Fehlermeldung mit einer URL, unter der ein neuerer Client heruntergeladen werden kann.

  - **URL** Wenn Sie **"Mit URL blockieren** " oder " **Mit URL zulassen**" ausgewählt haben, können Sie die URL für den Clientdownload angeben, die in die Fehlermeldung eingeschlossen werden soll.

Ausführliche Informationen zur Interoperabilität zwischen Clients und Clientversionen finden Sie unter [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von Clientversionskonfigurationen finden Sie unter [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) in der Betriebsdokumentation.