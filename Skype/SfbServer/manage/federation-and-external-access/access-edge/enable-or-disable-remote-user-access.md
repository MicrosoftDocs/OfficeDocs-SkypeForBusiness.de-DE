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
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Wenn Sie den Remotebenutzerzugriff für Remotebenutzer aktivieren, werden die unterstützten Remotebenutzer über das Internet verbunden und müssen nicht über ein VPN eine Verbindung herstellen, um mit internen Benutzern über Skype for Business Server zusammenzuarbeiten.
ms.openlocfilehash: dde2bbb2d71d84bc9102683afc37208e3c4616bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280236"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a>Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in Skype for Business Server

Bei Remote Benutzern handelt es sich um Benutzer in Ihrer Organisation, die eine persistente Active Directory-Identität innerhalb der Organisation aufweisen. Remote Benutzer können sich häufig über ein virtuelles privates Netzwerk (VPN) bei Skype for Business Server von außerhalb Ihres Netzwerks anmelden, wenn diese nicht mit dem Netzwerk Ihrer Organisation verbunden sind. Zu den Remotebenutzern gehören Mitarbeiter, die zu Hause oder unterwegs arbeiten, und andere Remotemitarbeiter, beispielsweise vertrauenswürdige Anbieter, denen Enterprise-Anmeldeinformationen gewährt wurden. Wenn Sie den Remotebenutzerzugriff für Remotebenutzer aktivieren, werden die unterstützten Remotebenutzer über das Internet verbunden und müssen nicht über ein VPN eine Verbindung herstellen, um mit internen Benutzern über Skype for Business Server zusammenzuarbeiten.

Wenn Sie den Zugriff durch Remotebenutzer unterstützen möchten, müssen Sie den Zugriff durch Remotebenutzer aktivieren. Wenn Sie den Remotebenutzerzugriff aktivieren, aktivieren Sie ihn für die gesamte Organisation. Wenn Sie später den Remotebenutzerzugriff vorübergehend oder dauerhaft verhindern möchten, können Sie ihn für Ihre Organisation deaktivieren. Verwenden Sie das Verfahren in diesem Abschnitt, um den Remotebenutzerzugriff für Ihre Organisation zu aktivieren oder zu deaktivieren.


> [!NOTE]  
> Das Aktivieren des Remotebenutzerzugriffs gibt nur an, dass Ihre Server, auf denen der Access Edge-Dienst ausgeführt wird, die Kommunikation mit Remotebenutzern unterstützen, aber Remotebenutzer nicht an Instant Messaging (im) oder Konferenzen in Ihrer Organisation teilnehmen können, bis Sie auch die Konfiguration unter mindestens eine Richtlinie zum Verwalten der Verwendung von Remotebenutzerzugriff. Skype for Business Server-Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden. Die Priorität der Skype for Business Server-Richtlinie lautet: Benutzerrichtlinien (der meiste Einfluss) überschreibt eine Website Richtlinie, und eine Website Richtlinie überschreibt eine globale Richtlinie (geringster Einfluss). Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt. Details zum Konfigurieren von Richtlinien für die Verwendung von Remotebenutzerzugriff finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Remotebenutzerzugriffs in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>So aktivieren oder deaktivieren Sie den Remotebenutzerzugriff für Ihre Organisation

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff** und dann auf **Zugriffs-Edgekonfiguration**.

4.  Klicken Sie auf der Seite **Access Edge Configuration** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Führen Sie in " **Access-Edge-Konfiguration bearbeiten**" eine der folgenden Aktionen aus:
    
      - Aktivieren Sie das Kontrollkästchen **Remotebenutzerzugriff aktivieren** , um den Remotebenutzerzugriff für Ihre Organisation zu aktivieren.
    
      - Deaktivieren Sie das Kontrollkästchen **Remotebenutzerzugriff aktivieren** , um den Remotebenutzerzugriff für Ihre Organisation zu deaktivieren.

6.  Klicken Sie auf **Commit ausführen**.

Damit Remotebenutzer sich bei ihren Servern mit Skype for Business Server anmelden können, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff konfigurieren, um den Zugriff durch Remotebenutzer zu unterstützen. Ausführliche Informationen finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Remotebenutzerzugriffs in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren des Remotebenutzerzugriffs mithilfe von Windows PowerShell-Cmdlets

Der Remote Benutzer Zugriff kann mithilfe von Windows PowerShell und dem Cmdlet "csaccessedgeconfiguration nicht angeben" verwaltet werden. Dieses Cmdlet kann entweder über die Skype for Business Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. 

## <a name="to-enable-remote-user-access"></a>So aktivieren Sie den Remotebenutzerzugriff

  - Um den Remotebenutzerzugriff zu aktivieren, legen Sie den Wert der **AllowOutsideUsers** -Eigenschaft auf true ($true) fest:
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a>So deaktivieren Sie den Remotebenutzerzugriff

  - Um den Remotebenutzerzugriff zu deaktivieren, legen Sie den Wert der **AllowOutsideUsers** -Eigenschaft auf false ($false) fest:
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


