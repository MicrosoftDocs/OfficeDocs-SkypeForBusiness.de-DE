---
title: Clientversionskonfiguration Erstellen einer neuen oder Bearbeiten einer vorhandenen Clientversionskonfiguration
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
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
ROBOTS: NOINDEX, NOFOLLOW
description: Konfigurationseinstellungen für Clientversion werden verwendet, um die Clientversionssteuerung zu aktivieren oder zu deaktivieren. Die globale Clientversionskonfiguration wird mit Skype for Business Server installiert und verwendet, um die Clientversionskontrolle für die gesamte Serverbereitstellung zu aktivieren oder zu deaktivieren. Wenn die globale Konfiguration aktiviert ist, werden alle von Ihnen verwendeten Clientversionsrichtlinien wirksam, wenn Benutzer versuchen, sich zu anmelden. Sie können die globale Clientversionskonfiguration deaktivieren, wenn keine Clientversionskontrolle erfolgen soll.
ms.openlocfilehash: e42d2c9e6d06bc72cd64de148454d28aab41483d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812365"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a>Clientversionskonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Clientversionskonfiguration

Konfigurationseinstellungen für Clientversion werden verwendet, um die Clientversionssteuerung zu aktivieren oder zu deaktivieren. Die globale Clientversionskonfiguration wird mit Skype for Business Server installiert und verwendet, um die Clientversionskontrolle für die gesamte Serverbereitstellung zu aktivieren oder zu deaktivieren. Wenn die globale Konfiguration aktiviert ist, werden alle von Ihnen verwendeten Clientversionsrichtlinien wirksam, wenn Benutzer versuchen, sich zu anmelden. Sie können die globale Clientversionskonfiguration deaktivieren, wenn keine Clientversionskontrolle erfolgen soll.

Sie können auch standortspezifische Clientversionskonfigurationen erstellen, um die Clientversionskontrolle pro Standort aktivieren und deaktivieren zu können. Standortspezifische Konfigurationen haben Vorrang vor der globalen Konfiguration.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Neue Clientversionskonfiguration erstellen** oder **Clientversionskonfiguration bearbeiten** können Sie die folgenden Aufgaben ausführen:

- Hinzufügen oder Ändern des Namens der Clientversionskonfiguration

- Aktivieren und Deaktivieren der Clientversionskontrolle global oder für einen bestimmten Standort

- Hinzufügen oder Ändern der Standardaktion für die Clientversionskonfiguration

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.

- **Bereich** Gibt den Bereich (Global oder Standort) der Clientversionskonfiguration an.

- **Name** Sie können den Namen der Clientversionskonfiguration hinzufügen oder ändern.

- **Aktivieren der Versionssteuerung** Je nach Umfang der Konfiguration können Sie die Clientversionskontrolle global oder für den Standort aktivieren oder deaktivieren.

- **Standardaktion** Sie können die Standardaktion auswählen, die angewendet wird, wenn ein Benutzer versucht, sich mit einer Clientanwendung zu anmelden, für die keine bestimmte Clientversionsrichtlinie besteht. Sie haben folgende Optionen:

  - **Zulassen** Ermöglicht dem Client die Anmeldung, wenn die Clientversion keinem Filter in der Liste der Clientversionsrichtlinien entsprechen.

  - **Block** Verhindert, dass sich der Client anmelden kann, wenn die Clientversion keinem Filter in der Liste der Clientversionsrichtlinien entsprechen.

  - **Block mit URL** Verhindert die Anmeldung des Clients, wenn die Clientversion keinem Filter in der Liste der Clientversionsrichtlinien entsprechen, und enthält eine Fehlermeldung mit einer URL, unter der ein neuerer Client heruntergeladen werden kann.

  - **Zulassen mit URL** Ermöglicht dem Client die Anmeldung, wenn die Clientversion keinem Filter in der Liste der Clientversionsrichtlinien entsprechen, und enthält eine Fehlermeldung mit einer URL, unter der ein neuerer Client heruntergeladen werden kann.

  - **URL** Wenn Sie **"Mit URL blockieren"** oder **"Mit URL** zulassen" ausgewählt haben, können Sie die Clientdownload-URL angeben, die in die Fehlermeldung enthalten sein soll.

Ausführliche Informationen zur Interoperabilität zwischen Clients und Clientversionen finden Sie unter [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von Clientversionskonfigurationen finden Sie unter [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in der Betriebsdokumentation.

