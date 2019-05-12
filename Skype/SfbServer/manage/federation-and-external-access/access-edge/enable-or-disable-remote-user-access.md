---
title: Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Wenn Sie den Zugriff durch Remotebenutzer für Remotebenutzer aktivieren, unterstützte Remotebenutzer über das Internet herstellen und müssen keine Verbindung herstellen über ein VPN, um die Zusammenarbeit mit internen Benutzern Skype für Business Server verwenden.
ms.openlocfilehash: 7586d6af408c4f6dd6290ccf1fc9f19dbc23a87e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919473"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a>Aktivieren Sie oder deaktivieren Sie des Zugriffs durch Remotebenutzer in Skype für Business Server

Remote-Benutzer sind Benutzer in Ihrer Organisation, die über eine beständige Active Directory-Identität innerhalb der Organisation verfügen. Remotebenutzer anmelden häufig zu Skype für Business Server von außerhalb des Netzwerks mithilfe von ein virtuelles privates Netzwerk (VPN), wenn sie nicht mit dem Netzwerk Ihrer Organisation verbunden sind. Remotebenutzer sind Mitarbeiter, die zu Hause arbeiten oder unterwegs sind und andere Remotemitarbeiter wie vertrauenswürdigen Anbieter, die erteilt worden Anmeldeinformationen für das Unternehmen. Wenn Sie den Zugriff durch Remotebenutzer für Remotebenutzer aktivieren, unterstützte Remotebenutzer über das Internet herstellen und müssen keine Verbindung herstellen über ein VPN, um die Zusammenarbeit mit internen Benutzern Skype für Business Server verwenden.

Zur Unterstützung des Zugriffs durch Remotebenutzer, müssen Sie den Zugriff durch Remotebenutzer aktivieren. Wenn Sie den Zugriff durch Remotebenutzer aktivieren, können Sie es für die gesamte Organisation. Wenn Sie später vorübergehend oder endgültig Zugriff durch Remotebenutzer verhindern möchten, können Sie es für Ihre Organisation deaktivieren. Verwenden Sie das Verfahren in diesem Abschnitt zum Aktivieren oder Deaktivieren der Zugriff durch Remotebenutzer für Ihre Organisation.


> [!NOTE]  
> Aktivieren des Zugriffs durch Remotebenutzer angegeben nur Servern mit Zugriffs-edgediensts unterstützen die Kommunikation mit Remotebenutzern, dass remote-Benutzer können nicht teilnehmen instant messaging (IM) oder Konferenzen in Ihrer Organisation, bis Sie auch auf Konfigurieren mindestens eine Richtlinie auf die Verwendung der des Zugriffs durch Remotebenutzer verwalten. Skype für Business Server aufgeführt, die auf einer Richtlinienebene angewendet werden kann Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden. Skype für Business Server RichtlinienPrioritäten ist: Benutzerrichtlinie (die meisten beeinflussen) überschreibt eine Standortrichtlinie, und klicken Sie dann eine Standortrichtlinie überschreibt eine globale Richtlinie (mindestens beeinflussen). Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt. Ausführliche Informationen zum Konfigurieren von Richtlinien für die Verwendung des Zugriffs durch Remotebenutzer finden Sie unter [Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch Remotebenutzer in Skype für Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>So aktivieren oder Deaktivieren der Zugriff durch Remotebenutzer für Ihre Organisation

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff** und dann auf **Zugriffs-Edgekonfiguration**.

4.  Klicken Sie auf der Seite **Konfiguration für Zugriffsedge** auf **Global**, klicken Sie auf **Bearbeiten**und klicken Sie dann auf **Details anzeigen**.

5.  Führen Sie in der **Konfiguration für Zugriffsedge bearbeiten**eine der folgenden Aktionen aus:
    
      - Um den Zugriff durch Remotebenutzer für Ihre Organisation zu aktivieren, aktivieren Sie das Kontrollkästchen **Zugriff durch Remotebenutzer aktivieren** .
    
      - Deaktivieren Sie das Kontrollkästchen **Zugriff durch Remotebenutzer aktivieren** , um den Zugriff durch Remotebenutzer für Ihre Organisation zu deaktivieren.

6.  Klicken Sie auf **Commit ausführen**.

Um Remotebenutzern zur Anmeldung bei Servern mit Skype für Business Server zu aktivieren, müssen Sie auch mindestens eine externe Zugriffsrichtlinie, um die Unterstützung des Zugriffs durch Remotebenutzer konfigurieren. Weitere Informationen hierzu finden Sie unter [Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch Remotebenutzer in Skype für Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer mithilfe von Windows PowerShell-cmdlets

Zugriff durch Remotebenutzer kann mithilfe von Windows PowerShell und das Set-CsAccessEdgeConfiguration-Cmdlet verwaltet werden. Dieses Cmdlet kann von der Skype für Business Server 2013-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung ausgeführt werden. 

## <a name="to-enable-remote-user-access"></a>Zum Aktivieren des Zugriffs durch Remotebenutzer

  - Um den Zugriff durch Remotebenutzer aktivieren, legen Sie den Wert der **AllowOutsideUsers** -Eigenschaft auf "true" ($True):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a>Deaktivieren des Zugriffs durch Remotebenutzer

  - Zum Deaktivieren des Zugriffs durch Remotebenutzer legen Sie den Wert der **AllowOutsideUsers** -Eigenschaft auf "false" ($False) fest:
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


