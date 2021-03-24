---
title: Clientversionskonfiguration Erstellen neuer oder Bearbeiten vorhandener Versionen
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
description: Konfigurationseinstellungen für Clientversion werden verwendet, um die Clientversionskontrolle ein- oder auszuschalten. Die Konfiguration der globalen Clientversion wird mit Skype for Business Server installiert und wird verwendet, um die Clientversionssteuerung für die gesamte Serverbereitstellung zu aktivieren oder zu deaktivieren. Wenn die globale Konfiguration aktiviert ist, werden alle von Ihnen verwendeten Clientversionsrichtlinien wirksam, wenn Benutzer versuchen, sich zu anmelden. Sie können die Konfiguration der globalen Clientversion deaktivieren, wenn kein Clientversionssteuerelement ausgeführt werden soll.
ms.openlocfilehash: 173bd8d2eb7ca47811497e07b8824aff6a4e6a20
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095629"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a>Clientversionskonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Clientversionskonfiguration

Konfigurationseinstellungen für Clientversion werden verwendet, um die Clientversionskontrolle ein- oder auszuschalten. Die Konfiguration der globalen Clientversion wird mit Skype for Business Server installiert und wird verwendet, um die Clientversionssteuerung für die gesamte Serverbereitstellung zu aktivieren oder zu deaktivieren. Wenn die globale Konfiguration aktiviert ist, werden alle von Ihnen verwendeten Clientversionsrichtlinien wirksam, wenn Benutzer versuchen, sich zu anmelden. Sie können die Konfiguration der globalen Clientversion deaktivieren, wenn kein Clientversionssteuerelement ausgeführt werden soll.

Sie können auch standortspezifische Clientversionskonfigurationen erstellen, um die Clientversionskontrolle pro Standort aktivieren und deaktivieren zu können. Standortspezifische Konfigurationen haben Vorrang vor der globalen Konfiguration.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Neue Clientversionskonfiguration erstellen** oder **Clientversionskonfiguration bearbeiten** können Sie die folgenden Aufgaben ausführen:

- Hinzufügen oder Ändern des Namens der Clientversionskonfiguration

- Aktivieren und Deaktivieren der Clientversionskontrolle global oder für einen bestimmten Standort

- Hinzufügen oder Ändern der Standardaktion für die Clientversionskonfiguration

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.

- **Bereich** Gibt den Bereich (Global oder Site) der Clientversionskonfiguration an.

- **Name** Sie können den Namen der Clientversionskonfiguration hinzufügen oder ändern.

- **Aktivieren der Versionssteuerung** Je nach Umfang der Konfiguration können Sie die Clientversionskontrolle global oder für den Standort aktivieren oder deaktivieren.

- **Standardaktion** Sie können die Standardaktion auswählen, die angewendet wird, wenn ein Benutzer versucht, sich mit einer Clientanwendung zu anmelden, für die keine bestimmte Clientversionsrichtlinie besteht. Sie haben folgende Optionen:

  - **Zulassen** Ermöglicht dem Client die Anmeldung, wenn die Clientversion keinem Filter in der Liste der Clientversionsrichtlinien zulässt.

  - **Blockieren** Verhindert, dass sich der Client anmelden kann, wenn die Clientversion keinem Filter in der Liste der Clientversionsrichtlinien entsprechen.

  - **Blockieren mit URL** Verhindert, dass sich der Client anmelden kann, wenn die Clientversion keinem Filter in der Liste der Clientversionsrichtlinien entsprechen, und enthält eine Fehlermeldung mit einer URL, in der ein neuerer Client heruntergeladen werden kann.

  - **Zulassen mit URL** Ermöglicht dem Client die Anmeldung, wenn die Clientversion keinem Filter in der Liste der Clientversionsrichtlinien entsprechen, und enthält eine Fehlermeldung mit einer URL, in der ein neuerer Client heruntergeladen werden kann.

  - **URL** Wenn Sie **Block with URL oder** Allow with **URL** ausgewählt haben, können Sie die Clientdownload-URL angeben, die in die Fehlermeldung enthalten sein soll.

Ausführliche Informationen zur Interoperabilität zwischen Clients und Clientversionen finden Sie unter [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von Clientversionskonfigurationen finden Sie unter [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) in der Betriebsdokumentation.