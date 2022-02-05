---
title: Planen der Ankündigungsanwendung in Skype for Business
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: 'Planung der Ankündigungsanwendung in Skype for Business Server Enterprise-VoIP, die konfiguriert, was mit Telefonanrufen für nicht zugewiesene Telefonnummern in Ihren Organisationen geschieht. Umfasst Audiodateianforderungen.'
---

# <a name="plan-for-the-announcement-application-in-skype-for-business"></a>Planen der Ankündigungsanwendung in Skype for Business

Planung der Ankündigungsanwendung in Skype for Business Server Enterprise-VoIP, die konfiguriert, was mit Telefonanrufen für nicht zugewiesene Telefonnummern in Ihren Organisationen geschieht. Umfasst Audiodateianforderungen.

Mit der Skype for Business Server Ankündigungsanwendung können Sie die Behandlung eingehender Telefonanrufe konfigurieren, wenn die gewählte Nummer für Ihre Organisation gültig ist, aber keinem Benutzer oder Telefon zugewiesen ist. Sie können diese Anrufe an ein vordefiniertes Ziel (Telefonnummer, SIP-URI oder Voicemail) übertragen oder eine Audioankündigung wiedergeben oder beides. Die Ansageanwendung hilft Ihnen, Situationen zu vermeiden, in denen ein Anrufer einen besetzten Ton hört oder der SIP-Client eine Fehlermeldung empfängt. Dieser Abschnitt enthält Planungsinformationen, die für die Ankündigungsanwendung spezifisch sind.

Wenn Sie die Ansageanwendung bereitstellen, müssen Sie eine Tabelle nicht zugewiesener Nummern konfigurieren, die bestimmt, welche Aktion ausgeführt werden soll, wenn jemand eine nicht zugewiesene Nummer wählt. Die Tabelle nicht zugewiesener Nummern enthält Telefonnummernbereiche, die für die Organisation gültig sind, und gibt an, welche Ankündigungsanwendung die einzelnen Bereiche verarbeitet. Wenn ein Anrufer eine Telefonnummer wählt, die für Ihre Organisation gültig ist, aber keiner zugewiesen ist, sucht Skype for Business Server die Nummer in der Routingtabelle für nicht zugewiesene Nummern, gibt an, in welchen Bereich die Nummer fällt, und leitet den Anruf an die für diesen Bereich angegebene Ankündigungsanwendung weiter. Die Ansageanwendung beantwortet den Anruf und gibt eine Audionachricht wieder (sofern Sie dies konfiguriert haben) und trennt den Anruf entweder oder überträgt ihn an ein vordefiniertes Ziel, z. B. an einen Operator. Sie können Skype for Business Server Verwaltungsshell-Cmdlets verwenden, um mehrere Audionachrichten zu konfigurieren oder Ziele zu übertragen.

Wie Sie die Tabelle nicht zugewiesener Rufnummern konfigurieren, richtet sich danach, wie Sie diese verwenden möchten. Wenn Sie über bestimmte Nummern verfügen, die nicht mehr verwendet werden, und Sie individuelle Nachrichten für jede dieser Nummern wiedergeben möchten, können Sie diese spezifischen Nummern in der Tabelle nicht zugewiesener Rufnummern eingeben. Wenn Sie beispielsweise die Nummer für Ihren Kundendienst ändern, können Sie die alte Rufnummer des Kundendiensts in die Tabelle eingeben und einer Ansage zuordnen, in der die neue Rufnummer bereitgestellt wird. Um eine allgemeine Nachricht für Anrufer wiederzugeben, die eine nicht zugewiesene Nummer wählen (z. B. für Mitarbeiter, die nicht länger für Ihre Organisation tätig sind), können Sie Bereiche für alle gültigen Durchwahlnummern in Ihrer Organisation angeben. Die Tabelle nicht zugewiesener Rufnummern wird aufgerufen, sobald ein Anrufer eine Nummer wählt, die gegenwärtig nicht zugewiesen ist.

## <a name="deployment-and-requirements"></a>Bereitstellung und Anforderungen

Die Ankündigungsanwendung wird automatisch mit der Reaktionsgruppenanwendung installiert. Die Ankündigungs- und Reaktionsgruppenanwendungen sind Standardkomponenten einer Enterprise-VoIP Bereitstellung: Wenn Sie Enterprise-VoIP bereitstellen, werden beide Anwendungen automatisch bereitgestellt.

### <a name="software-requirements"></a>Softwareanforderungen

Auf allen Front-End-Servern oder Standard Edition Servern, auf denen die Ankündigungsanwendung ausgeführt wird, muss die Windows Media Format Runtime für Server mit Windows Server 2008 R2 oder Microsoft Media Foundation für Server mit Windows Server 2012 oder Windows Server 2012  R2. For Windows Server 2008 R2, the Windows Media Format Runtime is installed as part of Windows Desktop Experience. Windows Media Format Runtime oder Microsoft Media Foundation ist für Windows WMA-Dateien (Media Audio) erforderlich, die von der Ankündigungsanwendung für Ankündigungen und Musik wiedergegeben werden.

### <a name="port-requirements"></a>Portanforderungen

Die Ankündigungsanwendung verwendet **Port 5071** für SIP-Überwachungsanforderungen.

> [!NOTE]
> Dieser Port ist die Standardeinstellung, die Sie mit dem Cmdlet **"Set-CsApplicationServer** " ändern können. Ausführliche Informationen zu diesem Cmdlet finden Sie in der Dokumentation zur Skype for Business Server Verwaltungsshell.

### <a name="audio-file-requirements"></a>Anforderungen für Audiodateien

Die Ankündigungsanwendung unterstützt das Wav-Dateiformat (Wave) und Windows WMA-Dateiformat (Media Audio) für Musik und Ankündigungen. Audiodateianforderungen für die Ansageanwendung sind die gleichen wie für die Reaktionsgruppenanwendung. Ausführliche Informationen finden Sie unter ["Technische Anforderungen für Reaktionsgruppen"](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).