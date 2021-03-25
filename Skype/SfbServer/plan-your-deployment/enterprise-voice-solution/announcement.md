---
title: Planen der Ankündigungsanwendung in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: Planen der Ankündigungsanwendung in Skype for Business Server Enterprise-VoIP, die konfiguriert, was mit Anrufen an nicht zugewiesene Telefonnummern in Ihrer Organisation zu tun ist. Enthält Audiodateianforderungen.
ms.openlocfilehash: e1309fe58942f3b9cd720b3643966ae9494bb0cb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112711"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a>Planen der Ankündigungsanwendung in Skype for Business

Planen der Ankündigungsanwendung in Skype for Business Server Enterprise-VoIP, die konfiguriert, was mit Anrufen an nicht zugewiesene Telefonnummern in Ihrer Organisation zu tun ist. Enthält Audiodateianforderungen.

Mit der Skype for Business Server-Ankündigungsanwendung können Sie die Behandlung eingehender Anrufe konfigurieren, wenn die gewählte Nummer für Ihre Organisation gültig ist, aber keinem Benutzer oder Telefon zugewiesen ist. Sie können diese Anrufe an ein vordefiniertes Ziel (Telefonnummer, SIP-URI oder Voicemail) übertragen oder eine Audioansage oder beides abspielen. Die Ansageanwendung hilft Ihnen, Situationen zu vermeiden, in denen ein Anrufer einen besetzten Ton anhört oder der SIP-Client eine Fehlermeldung empfängt. Dieser Abschnitt enthält Planungsinformationen, die für die Ankündigungsanwendung spezifisch sind

Wenn Sie die Ankündigungsanwendung bereitstellen, müssen Sie eine Tabelle nicht zugewiesener Nummern konfigurieren, die die Aktion bestimmt, die beim Wählen einer nicht zugewiesenen Nummer ergriffen werden soll. Die Tabelle nicht zugewiesene Nummern enthält Bereiche von Telefonnummern, die für die Organisation gültig sind, und gibt an, welche Ankündigungsanwendung jeden Bereich verarbeitet. Wenn ein Anrufer eine Telefonnummer wählt, die für Ihre Organisation gültig ist, aber niemandem zugewiesen ist, sucht Skype for Business Server die Nummer in der Routingtabelle nicht zugewiesener Nummern, identifiziert den Bereich, in den die Nummer fällt, und leitet den Anruf an die für den Bereich angegebene Ansageanwendung weiter. Die Ansageanwendung beantwortet den Anruf und gibt eine Audionachricht ab (wenn Sie dies konfiguriert haben), und trennt den Anruf dann entweder oder überträgt ihn an ein vordefiniertes Ziel, z. B. an einen Operator. Sie können Skype for Business Server Management Shell-Cmdlets verwenden, um mehrere Audionachrichten zu konfigurieren oder Ziele zu übertragen.

Wie Sie die Tabelle nicht zugewiesener Rufnummern konfigurieren, richtet sich danach, wie Sie diese verwenden möchten. Wenn Sie über bestimmte Nummern verfügen, die nicht mehr verwendet werden, und Sie individuelle Nachrichten für jede dieser Nummern wiedergeben möchten, können Sie diese spezifischen Nummern in der Tabelle nicht zugewiesener Rufnummern eingeben. Wenn Sie beispielsweise die Nummer für Ihren Kundendienst ändern, können Sie die alte Rufnummer des Kundendiensts in die Tabelle eingeben und einer Ansage zuordnen, in der die neue Rufnummer bereitgestellt wird. Um eine allgemeine Nachricht für Anrufer wiederzugeben, die eine nicht zugewiesene Nummer wählen (z. B. für Mitarbeiter, die nicht länger für Ihre Organisation tätig sind), können Sie Bereiche für alle gültigen Durchwahlnummern in Ihrer Organisation angeben. Die Tabelle nicht zugewiesener Rufnummern wird aufgerufen, sobald ein Anrufer eine Nummer wählt, die gegenwärtig nicht zugewiesen ist.

## <a name="deployment-and-requirements"></a>Bereitstellung und Anforderungen

Die Ankündigungsanwendung wird automatisch mit der Reaktionsgruppe-Anwendung installiert. Die Ansage- und Reaktionsgruppeanwendungen sind Standardkomponenten einer Enterprise-VoIP Bereitstellung: Wenn Sie Enterprise-VoIP bereitstellen, werden beide Anwendungen automatisch bereitgestellt.

### <a name="software-requirements"></a>Softwareanforderungen

Auf allen Front-End-Servern oder Standard Edition-Servern, auf denen die Ankündigungsanwendung ausgeführt wird, muss die Windows Media Format Runtime für Server mit Windows Server 2008 R2 oder Microsoft Media Foundation für Server mit Windows Server 2012 oder Windows Server 2012 R2 installiert sein. Für Windows Server 2008 R2 wird die Windows Media Format Runtime als Teil der Windows Desktop Experience installiert. Windows Media Format Runtime oder Microsoft Media Foundation ist für Windows Media Audio (WMA)-Dateien erforderlich, die von der Ankündigungsanwendung für Ansagen und Musik abspielen.

### <a name="port-requirements"></a>Portanforderungen

Die Ankündigungsanwendung verwendet **Port 5071 für** SIP-Abhöranforderungen.

> [!NOTE]
> Dieser Port ist die Standardeinstellung, die Sie mit dem **Cmdlet Set-CsApplicationServer** ändern können. Ausführliche Informationen zu diesem Cmdlet finden Sie in der Dokumentation zur Skype for Business Server Management Shell.

### <a name="audio-file-requirements"></a>Anforderungen für Audiodateien

Die Ankündigungsanwendung unterstützt das Wave-Dateiformat (WAV) und das Windows Media-Audio-Dateiformat (WMA) für Musik und Ankündigungen. Die Anforderungen an Audiodateien für die Ankündigungsanwendung sind mit den Anforderungen für die Reaktionsgruppe identisch. Weitere Informationen finden Sie unter [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).