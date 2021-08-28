---
title: Erstellen einer neuen oder Bearbeiten einer vorhandenen Clientversionskonfiguration
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
ROBOTS: NOINDEX, NOFOLLOW
description: Clientversionskonfigurationseinstellungen werden verwendet, um die Clientversionskontrolle zu aktivieren oder zu deaktivieren. Die globale Clientversionskonfiguration wird mit Skype for Business Server installiert und wird verwendet, um die Clientversionskontrolle für die gesamte Serverbereitstellung zu aktivieren oder zu deaktivieren. Wenn die globale Konfiguration aktiviert ist, werden alle clientversionsrichtlinien, die Sie eingerichtet haben, wirksam, wenn Benutzer versuchen, sich anzumelden. Sie können die globale Clientversionskonfiguration deaktivieren, wenn keine Clientversionskontrolle erfolgen soll.
ms.openlocfilehash: c43ae2a58a7a42e23408f5f9c0ad627fe8db5a63
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58608532"
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

- **Bereich** Gibt den Bereich (global oder Standort) der Clientversionskonfiguration an.

- **Name** Sie können den Namen der Clientversionskonfiguration hinzufügen oder ändern.

- **Aktivieren der Versionskontrolle** Sie können die Clientversionskontrolle je nach Konfigurationsumfang global oder für den Standort aktivieren oder deaktivieren.

- **Standardaktion** Sie können die Standardaktion auswählen, die angewendet wird, wenn ein Benutzer versucht, sich mit einer Clientanwendung anzumelden, für die keine bestimmte Clientversionsrichtlinie vorhanden ist. Sie haben folgende Optionen:

  - **Zulassen** Ermöglicht dem Client die Anmeldung, wenn die Clientversion keinem Filter in der Liste der Clientversionsrichtlinien entspricht.

  - **Blockieren** Verhindert, dass sich der Client anmeldet, wenn die Clientversion keinem Filter in der Liste der Clientversionsrichtlinien entspricht.

  - **Blockieren mit URL** Verhindert, dass sich der Client anmeldet, wenn die Clientversion keinem Filter in der Liste der Clientversionsrichtlinien entspricht, und enthält eine Fehlermeldung mit einer URL, unter der ein neuerer Client heruntergeladen werden kann.

  - **Zulassen mit URL** Ermöglicht dem Client die Anmeldung, wenn die Clientversion keinem Filter in der Liste der Clientversionsrichtlinien entspricht, und enthält eine Fehlermeldung mit einer URL, unter der ein neuerer Client heruntergeladen werden kann.

  - **URL** Wenn Sie **"Mit URL blockieren"** oder **"Mit URL zulassen"** ausgewählt haben, können Sie die Url für den Clientdownload angeben, die in die Fehlermeldung eingeschlossen werden soll.

Ausführliche Informationen zur Interoperabilität zwischen Clients und Clientversionen finden Sie in der Planungsdokumentation unter ["Clientinteroperabilität".](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) Ausführliche Informationen zur Verwendung von Clientversionskonfigurationen finden Sie unter [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) in der Betriebsdokumentation.