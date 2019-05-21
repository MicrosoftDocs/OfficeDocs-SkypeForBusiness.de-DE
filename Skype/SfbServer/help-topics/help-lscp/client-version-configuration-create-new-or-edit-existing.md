---
title: Client-Versions Konfiguration neues erstellen oder vorhandenes bearbeiten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
description: Client Version-Konfigurationseinstellungen werden verwendet, um die Client Versionskontrolle zu aktivieren oder zu deaktivieren. Die Konfiguration der globalen Client Version wird mit Skype for Business Server installiert und wird verwendet, um die Client Versionskontrolle für die gesamte Server Bereitstellung zu aktivieren oder zu deaktivieren. Wenn die globale Konfiguration aktiviert ist, werden alle von Ihnen eingerichteten clientversionsrichtlinien wirksam, wenn Benutzer versuchen, sich anzumelden. Sie können die Konfiguration der globalen Client Version deaktivieren, wenn keine Client Versionskontrolle erfolgen soll.
ms.openlocfilehash: 1a42f2a355ead1d98e7e8031b43db879f271dced
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300056"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a>Clientversionskonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Clientversionskonfiguration

Client Version-Konfigurationseinstellungen werden verwendet, um die Client Versionskontrolle zu aktivieren oder zu deaktivieren. Die Konfiguration der globalen Client Version wird mit Skype for Business Server installiert und wird verwendet, um die Client Versionskontrolle für die gesamte Server Bereitstellung zu aktivieren oder zu deaktivieren. Wenn die globale Konfiguration aktiviert ist, werden alle von Ihnen eingerichteten clientversionsrichtlinien wirksam, wenn Benutzer versuchen, sich anzumelden. Sie können die Konfiguration der globalen Client Version deaktivieren, wenn keine Client Versionskontrolle erfolgen soll.

Sie können auch standortspezifische Clientversionskonfigurationen erstellen, um die Clientversionskontrolle pro Standort aktivieren und deaktivieren zu können. Standortspezifische Konfigurationen haben Vorrang vor der globalen Konfiguration.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Neue Clientversionskonfiguration erstellen** oder **Clientversionskonfiguration bearbeiten** können Sie die folgenden Aufgaben ausführen:

- Hinzufügen oder Ändern des Namens der Clientversionskonfiguration

- Aktivieren und Deaktivieren der Clientversionskontrolle global oder für einen bestimmten Standort

- Hinzufügen oder Ändern der Standardaktion für die Clientversionskonfiguration

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.

- **Bereich** Identifiziert den Bereich (Global oder Website) der Client Versions Konfiguration.

- **Name** Sie können den Namen der Client Versions Konfiguration hinzufügen oder ändern.

- **Aktivieren der Versionskontrolle** Je nach dem Umfang der Konfiguration können Sie die Client Versionskontrolle Global oder für die Website aktivieren oder deaktivieren.

- **Standardaktion** Sie können die Standardaktion auswählen, die angewendet werden soll, wenn ein Benutzer versucht, sich mit einer Clientanwendung anzumelden, für die es keine spezifische clientversionsrichtlinie gibt. Sie haben folgende Optionen:

  - **Zulassen** Ermöglicht es dem Client, sich anzumelden, wenn die Client Version keinem Filter in der Liste der clientversionsrichtlinien entspricht.

  - **Blockieren** Verhindert, dass der Client sich anmeldet, wenn die Client Version keinem Filter in der Liste der clientversionsrichtlinien entspricht.

  - **Block mit URL** Verhindert, dass der Client sich anmeldet, wenn die Client Version keinem Filter in der Liste der clientversionsrichtlinien entspricht und eine Fehlermeldung mit einer URL enthält, in der ein neuerer Client heruntergeladen werden kann.

  - **Mit URL zulassen** Ermöglicht es dem Client, sich anzumelden, wenn die Client Version keinem Filter in der Liste der clientversionsrichtlinien entspricht und eine Fehlermeldung mit einer URL enthält, in der ein neuerer Client heruntergeladen werden kann.

  - **URL** Wenn Sie **Block mit URL** oder **Allow with URL**ausgewählt haben, können Sie die Client Download-URL angeben, die in die Fehlermeldung aufgenommen werden soll.

Ausführliche Informationen zur Interoperabilität zwischen Clients und Clientversionen finden Sie in der Planungsdokumentation unter [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx). Ausführliche Informationen zur Verwendung von Clientversionskonfigurationen finden Sie in der Betriebsdokumentation unter [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx).

