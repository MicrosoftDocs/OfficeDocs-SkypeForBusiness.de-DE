---
title: Systemsteuerung – Übersicht
ms.reviewer: ''
ms.author: v-smandalika
author: v-smandalika
manager: dansimp
ms.date: 10/13/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: Dieser Artikel bietet eine Übersicht über die neue Systemsteuerung.
ms.openlocfilehash: 77e26b810bfd61effa5d94ec3648c440476a7cbe
ms.sourcegitcommit: eba9fc680233e9e03773a2942f22afe6247eec41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60824643"
---
# <a name="control-panel"></a>Systemsteuerung

Die aktuelle Systemsteuerung ist eine neue Version der älteren Systemsteuerung, mit der sie zusammen vorhanden ist. Die neue Systemsteuerung ist aus dem kumulativen Update vom Juli 2019 entstanden. Es hilft bei der Verwaltung der Konfiguration von Servern, Benutzern, Clients und Geräten in der Umgebung einer Organisation.

Die alte Systemsteuerung funktioniert möglicherweise nicht, da die Silverlight-Technologie am 12. Oktober 2021 die Phase "Ende des Supports" erreicht hat. Weitere Informationen finden Sie unter [Silverlight-Supportende.](https://support.microsoft.com/windows/silverlight-end-of-support-0a3be3c7-bead-e203-2dfd-74f0a64f1788)

> [!NOTE]
> Informationen zur älteren Systemsteuerung finden Sie in der [Systemsteuerung,](../SfbServer/management-tools/install-and-open-administrative-tools.md)und navigieren Sie zum Abschnitt **Skype for Business Server Systemsteuerung.**

## <a name="access-control-panel"></a>Zugriffssteuerung

Um die neue Systemsteuerung im Browser zu starten, geben Sie https:// &lt; Pool-FQDN &gt; /macp oder eine konfigurierte einfache URL ein.

Die neue Systemsteuerung enthält häufig verwendete Menüelemente, die die meisten Anforderungen der Organisation erfüllen. Es gibt einige Menüelemente aus der älteren Systemsteuerung, die in der neuen Systemsteuerung nicht verfügbar sind. Es gibt jedoch eine Option für den Benutzer, die Funktionen in diesen Menüelementen über PowerShell-Cmdlets zu nutzen. Weitere Informationen finden Sie in der tabelle unten.

> [!NOTE]
> Die Dokumentation für andere Menüelemente wird anschließend phasenweise zur Verfügung gestellt.

## <a name="client"></a>Client

|Untermenü  |Informationsquelle für Cmdlet  |
|---------|---------|
|Clientversionsrichtlinie         |    [Clientversionsrichtlinie](use-powershell-client-menu.md#client-version-policy)     |
|Clientversionskonfiguration      |  [Clientversionskonfiguration](use-powershell-client-menu.md#client-version-configuration)       |
|Geräteaktualisierung    | [Geräteaktualisierung](use-powershell-client-menu.md#device-update)        |
|Testgerät     | [Testgerät](use-powershell-client-menu.md#test-device)        |
|Geräteprotokollkonfiguration         |    [Geräteprotokollkonfiguration](use-powershell-client-menu.md#device-log-configuration)     |
|Gerätekonfiguration         |    [Gerätekonfiguration](use-powershell-client-menu.md#device-configuration)     |
|Mobilitätsrichtlinie         |    [Mobilitätsrichtlinie](use-powershell-client-menu.md#mobility-policy)     |
|Konfiguration von Pushbenachrichtigungen         |    [Konfiguration von Pushbenachrichtigungen](use-powershell-client-menu.md#push-notification-configuration)     |

## <a name="security"></a>Sicherheit

|Untermenü  |Informationsquelle für Cmdlet  |
|---------|---------|
|Registrar         |    [Registrar](use-powershell-security-menu.md#registrar)     |
|Webdienst      |  [Webdienst](use-powershell-security-menu.md#web-service)       |
|PIN-Richtlinie    | [PIN-Richtlinie](use-powershell-security-menu.md#pin-policy)        |
