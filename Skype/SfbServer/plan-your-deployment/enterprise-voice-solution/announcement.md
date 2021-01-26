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
description: Planung für die Ansageanwendung in Skype for Business Server Enterprise-VoIP, die konfiguriert, was mit Anrufen an nicht zugewiesene Telefonnummern in Ihrer Organisation zu tun ist. Umfasst Audiodateianforderungen.
ms.openlocfilehash: b1929fa14b105fd8eccd0f178ae7ef77c1bdf086
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813755"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a>Planen der Ankündigungsanwendung in Skype for Business

Planung für die Ansageanwendung in Skype for Business Server Enterprise-VoIP, die konfiguriert, was mit Anrufen an nicht zugewiesene Telefonnummern in Ihrer Organisation zu tun ist. Umfasst Audiodateianforderungen.

Mit der Ansageanwendung für Skype for Business Server können Sie die Verarbeitung eingehender Telefonanrufe konfigurieren, wenn die gewählte Nummer für Ihre Organisation gültig ist, aber keinem Benutzer oder Telefon zugewiesen ist. Sie können diese Anrufe an ein vordefiniertes Ziel (Telefonnummer, SIP-URI oder Voicemail) übertragen oder eine Audioansage oder beides abspielen. Die Ansageanwendung hilft Ihnen, Situationen zu vermeiden, in denen ein Anrufer einen Besetztton abhört oder der SIP-Client eine Fehlermeldung empfängt. Dieser Abschnitt enthält Planungsinformationen speziell für die Ankündigungsanwendung.

Wenn Sie die Ansageanwendung bereitstellen, müssen Sie eine Tabelle nicht zugewiesener Nummern konfigurieren, die bestimmt, welche Aktion beim Wählen einer nicht zugewiesenen Nummer ergriffen werden soll. Die Tabelle nicht zugewiesener Nummern enthält Nummernbereiche, die für die Organisation gültig sind, und gibt an, welche Ansageanwendung die einzelnen Bereiche verarbeitet. Wenn ein Anrufer eine Telefonnummer wählt, die für Ihre Organisation gültig ist, aber niemandem zugewiesen ist, sucht Skype for Business Server die Nummer in der Routingtabelle für nicht zugewiesene Nummern, identifiziert den Bereich, in den die Nummer fällt, und leitet den Anruf an die für den Bereich angegebene Ansageanwendung weiter. Die Ansageanwendung nimmt den Anruf an und gibt eine Audionachricht wieder (sofern Sie dies konfiguriert haben) und trennt dann den Anruf oder überträgt ihn an ein vordefiniertes Ziel, z. B. an eine Telefongesellschaft. Mithilfe von Skype for Business Server Management Shell-Cmdlets können Sie mehrere Audionachrichten konfigurieren oder Ziele übertragen.

Wie Sie die Tabelle nicht zugewiesener Rufnummern konfigurieren, richtet sich danach, wie Sie diese verwenden möchten. Wenn Sie über bestimmte Nummern verfügen, die nicht mehr verwendet werden, und Sie individuelle Nachrichten für jede dieser Nummern wiedergeben möchten, können Sie diese spezifischen Nummern in der Tabelle nicht zugewiesener Rufnummern eingeben. Wenn Sie beispielsweise die Nummer für Ihren Kundendienst ändern, können Sie die alte Rufnummer des Kundendiensts in die Tabelle eingeben und einer Ansage zuordnen, in der die neue Rufnummer bereitgestellt wird. Um eine allgemeine Nachricht für Anrufer wiederzugeben, die eine nicht zugewiesene Nummer wählen (z. B. für Mitarbeiter, die nicht länger für Ihre Organisation tätig sind), können Sie Bereiche für alle gültigen Durchwahlnummern in Ihrer Organisation angeben. Die Tabelle nicht zugewiesener Rufnummern wird aufgerufen, sobald ein Anrufer eine Nummer wählt, die gegenwärtig nicht zugewiesen ist.

## <a name="deployment-and-requirements"></a>Bereitstellung und Anforderungen

Die Ansageanwendung wird automatisch mit der Reaktionsgruppe installiert. Die Ansage- und Reaktionsgruppesanwendungen sind Standardkomponenten einer Enterprise-VoIP Bereitstellung: Wenn Sie Enterprise-VoIP bereitstellen, werden beide Anwendungen automatisch bereitgestellt.

### <a name="software-requirements"></a>Softwareanforderungen

Auf allen Front-End-Servern oder Standard Edition-Servern, auf denen die Ansageanwendung ausgeführt wird, muss die Windows Media Format Runtime für Server mit Windows Server 2008 R2 oder Microsoft Media Foundation für Server mit Windows Server 2012 oder Windows Server 2012 R2 installiert sein. For Windows Server 2008 R2, the Windows Media Format Runtime is installed as part of Windows Desktop Experience. Windows Media Format Runtime oder Microsoft Media Foundation ist für Windows Media Audio (.wma)-Dateien erforderlich, die von der Ansageanwendung für Ansagen und Musik abspielt werden.

### <a name="port-requirements"></a>Portanforderungen

Die Ansageanwendung verwendet **Port 5071 für** SIP-Abhöranforderungen.

> [!NOTE]
> Dieser Port ist die Standardeinstellung, die Sie mit dem **Cmdlet "Set-CsApplicationServer"** ändern können. Ausführliche Informationen zu diesem Cmdlet finden Sie in der Dokumentation zur Skype for Business Server-Verwaltungsshell.

### <a name="audio-file-requirements"></a>Anforderungen für Audiodateien

Die Ansageanwendung unterstützt das Wav-Dateiformat (Wave) und das Windows Media Audio (WMA)-Dateiformat für Musik und Ansagen. Die Audiodateianforderungen für die Ansageanwendung sind mit den Anforderungen für die Reaktionsgruppe identisch. Weitere Informationen finden Sie unter ["Technische Anforderungen für Reaktionsgruppen".](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)


