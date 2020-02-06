---
title: Planen der Ankündigungs Anwendung in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Planen der Ankündigungs Anwendung in Skype for Business Server Enterprise-VoIP, mit der festgelegt wird, was mit Telefon anrufen an nicht zugewiesene Telefonnummern in ihren Organisationen zu tun ist. Es konfiguriert, was mit nicht zugewiesenen Telefonnummern in Ihren Organisationen passiert und beinhaltet Audiodateianforderungen.
ms.openlocfilehash: d160878030fad30dd3e91b78f54ffcdab722299f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803265"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a>Planen der Ankündigungs Anwendung in Skype for Business

Planen der Ankündigungs Anwendung in Skype for Business Server Enterprise-VoIP, mit der festgelegt wird, was mit Telefon anrufen an nicht zugewiesene Telefonnummern in ihren Organisationen zu tun ist. Es konfiguriert, was mit nicht zugewiesenen Telefonnummern in Ihren Organisationen passiert und beinhaltet Audiodateianforderungen.

Mit der Skype for Business Server-Ankündigungs Anwendung können Sie die Behandlung von eingehenden Telefon anrufen konfigurieren, wenn die gewählte Nummer für Ihre Organisation gültig ist, aber nicht einem Benutzer oder einem Telefon zugewiesen ist. Sie können diese Anrufe an ein vorab festgelegtes Ziel (Rufnummer, SIP-URI oder Voicemail) übergeben oder eine Audioansage wiedergeben oder beides. Mithilfe der Ansageanwendung können Sie Situationen verhindern, in denen sich ein Anrufer verwählt und ein Besetztzeichen hört oder der SIP-Client eine Fehlermeldung erhält. Dieser Abschnitt enthält Planungsinformationen, die für die Ankündigungs Anwendung spezifisch sind.

Wenn Sie die Ankündigungs Anwendung bereitstellen, müssen Sie eine Tabelle mit nicht zugewiesener Nummer konfigurieren, die bestimmt, welche Aktion ausgeführt werden soll, wenn eine andere Person eine nicht zugewiesene Nummer wählt. Die Tabelle "nicht zugewiesene Nummer" enthält Bereiche von Telefonnummern, die für die Organisation gültig sind, und gibt an, welche Ankündigungs Anwendung die einzelnen Bereiche verarbeitet. Wenn ein Anrufer eine Telefonnummer wählt, die für Ihre Organisation gültig ist, aber keiner Person zugewiesen ist, sucht Skype for Business Server die Nummer in der Routingtabelle nicht zugewiesene Nummer, gibt den Bereich an, in den die Nummer fällt, und leitet den Anruf an die Für diesen Bereich angegebene Ankündigungs Anwendung. Die Ankündigungs Anwendung beantwortet den Anruf und gibt eine Audionachricht wieder, wenn Sie Sie so konfiguriert haben, und trennt dann entweder den Anruf oder übergibt ihn an ein festgelegtes Ziel, beispielsweise an einen Operator. Sie können Cmdlets für die Skype for Business Server-Verwaltungsshell verwenden, um mehrere Audionachrichten zu konfigurieren oder Ziele zu übertragen.

Wie Sie die Tabelle nicht zugewiesener Rufnummern konfigurieren, richtet sich danach, wie Sie sie verwenden möchten. Wenn Sie über bestimmte Nummern verfügen, die nicht mehr verwendet werden, und individuelle Nachrichten für jede dieser Nummern wiedergeben möchten, können Sie diese spezifischen Nummern in die Tabelle nicht zugewiesener Rufnummern eingeben. Wenn Sie beispielsweise die Nummer für Ihren Kundendienst ändern, können Sie die alte Rufnummer des Kundendiensts in die Tabelle eingeben und einer Ansage zuordnen, in der die neue Rufnummer bereitgestellt wird. Um eine allgemeine Nachricht für Anrufer wiederzugeben, die eine nicht zugewiesene Nummer wählen (z. B. für Mitarbeiter, die nicht mehr für Ihre Organisation tätig sind), können Sie Bereiche für alle gültigen Durchwahlnummern in Ihrer Organisation angeben. Die Tabelle nicht zugewiesener Rufnummern wird aufgerufen, sobald ein Anrufer eine Nummer wählt, die gegenwärtig nicht zugewiesen ist.

## <a name="deployment-and-requirements"></a>Bereitstellungen und Anforderungen

Die Ankündigungs Anwendung wird automatisch mit der Antwortgruppen Anwendung installiert. Die Anwendungen für Ankündigungen und Reaktionsgruppen sind Standardkomponenten einer Enterprise-VoIP-Bereitstellung: Wenn Sie Enterprise-VoIP bereitstellen, werden diese beiden Anwendungen automatisch bereitgestellt.

### <a name="software-requirements"></a>Softwareanforderungen

Auf allen Front-End-Servern oder Standard Edition-Servern, auf denen die Ankündigungs Anwendung ausgeführt wird, muss die Windows Media-Format Laufzeit für Server mit Windows Server 2008 R2 oder Microsoft Media Foundation für Server mit Windows Server 2012 oder Windows Server 2012 R2 Bei Windows Server 2008 R2 wird die Windows Media-Format Laufzeit als Teil der Windows-Desktop Oberfläche installiert. Windows Media Format Runtime oder Microsoft Media Foundation ist für Windows Media Audio-Dateien (WMA) erforderlich, die von der Ankündigungs Anwendung für Ankündigungen und Musik wiedergegeben werden.

### <a name="port-requirements"></a>Portanforderungen

Die Ankündigungs Anwendung verwendet **Port 5071** für SIP-Überwachungsanforderungen.

> [!NOTE]
> Dieser Port ist die Standardeinstellung, kann aber mit dem Cmdlet **Set-CsApplicationServer** geändert werden. Details zu diesem Cmdlet finden Sie in der Dokumentation zur Skype for Business Server-Verwaltungsshell.

### <a name="audio-file-requirements"></a>Anforderungen für Audiodateien

Die Ankündigungs Anwendung unterstützt das Wave-Dateiformat (WAV) und das Windows Media Audio-Dateiformat (WMA) für Musik und Ankündigungen. Die Anforderungen an die Audiodateien für die Ankündigungs Anwendung sind identisch mit der Antwortgruppen Anwendung. Ausführliche Informationen finden Sie unter [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).


