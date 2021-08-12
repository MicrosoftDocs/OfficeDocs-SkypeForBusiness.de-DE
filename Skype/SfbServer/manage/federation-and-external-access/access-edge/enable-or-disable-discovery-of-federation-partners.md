---
title: Aktivieren oder Deaktivieren der Suche von Verbundpartnern
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Nachdem Sie Ihre Edgeserver bereitgestellt und den Partnerverbund für Ihre Organisation aktiviert haben, sollten Sie festlegen, ob die automatische Suche von Verbundpartnerdomänen unterstützt werden soll.
ms.openlocfilehash: c66dd9750c8fdd36af5fad75f40b6939a04b0971cec4c9e57fe97bd06047ed9d
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2021
ms.locfileid: "57849190"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a>Aktivieren oder Deaktivieren der Ermittlung von Verbundpartnern in Skype for Business Server

Nachdem Sie Ihre Edgeserver bereitgestellt und den Partnerverbund für Ihre Organisation aktiviert haben, sollten Sie festlegen, ob die automatische Suche von Verbundpartnerdomänen unterstützt werden soll. Verwenden Sie das Verfahren in diesem Thema, um diese Konfiguration zu ändern.

> [!NOTE]  
> Im folgenden Verfahren wird vorausgesetzt, dass Sie den Partnerverbund für Ihre Organisation bereits aktiviert haben. Ausführliche Informationen zum Aktivieren des Partnerverbunds finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs.](enable-or-disable-remote-user-access.md)

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>So aktivieren oder deaktivieren Sie die automatische Suche von Partnerdomänen für Ihre Organisation

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Konfiguration für Zugriffsedge**.

4.  Klicken Sie auf der Seite **Konfiguration für Zugriffsedge** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Aktivieren oder deaktivieren Sie im Abschnitt **Konfiguration für Zugriffsedge bearbeiten** unter **Kommunikation mit Partnerbenutzern aktivieren** das Kontrollkästchen **Suche von Partnerdomänen aktivieren**, um die automatische Suche von Partnerdomänen zu aktivieren bzw. zu deaktivieren.

6.  Klicken Sie auf **Commit**.

Damit Verbundbenutzer mit Benutzern in Ihrer Skype for Business Server Bereitstellung zusammenarbeiten können, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff konfiguriert haben, um den Zugriff durch Verbundbenutzer zu unterstützen. Ausführliche Informationen finden Sie unter Aktivieren oder Deaktivieren des [Partnerverbunds und der Verbindung mit öffentlichen Chatdiensten.](enable-or-disable-federation-and-public-im-connectivity.md) Ausführliche Informationen zum Steuern des Zugriffs für bestimmte Verbunddomänen finden Sie unter [Verwalten von SIP-Partnerverbunddomänen](../sip-domains/manage-sip-federated-domains-for-your-organization.md) und [Verwalten von SIP-Partnerverbundanbietern.](../sip-providers/manage-sip-federated-providers-for-your-organization.md)


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren der Ermittlung von Verbundpartnern mithilfe Windows PowerShell Cmdlets

Die Ermittlung von Verbundpartnern kann mithilfe von Windows PowerShell und dem cmdlet Set-CsAccessEdgeConfiguration verwaltet werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. 


## <a name="to-enable-discovery-of-federation-partners"></a>So aktivieren Sie die Ermittlung von Verbundpartnern

  - Legen Sie zur Aktivierung der Ermittlung von Verbundpartnern den Wert der Eigenschaft **EnablePartnerDiscovery** auf "True" ($True) fest. Beachten Sie, dass Sie DNS-SRV-Routing aktivieren müssen, um diesen Eigenschaftswert zu ändern.<br/><br/>Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a>So deaktivieren Sie die Ermittlung von Verbundpartnern

  - Legen Sie zur Deaktivierung der Ermittlung von Verbundpartnern den Wert der Eigenschaft **EnablePartnerDiscovery** auf "False" ($False) fest:<br/><br/>Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

