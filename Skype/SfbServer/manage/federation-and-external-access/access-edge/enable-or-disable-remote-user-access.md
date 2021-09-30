---
title: Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Wenn Sie den Remotebenutzerzugriff für Remotebenutzer aktivieren, stellen unterstützte Remotebenutzer eine Verbindung über das Internet her und müssen keine VPN-Verbindung herstellen, um mit internen Benutzern über Skype for Business Server zusammenzuarbeiten.
ms.openlocfilehash: 743ec476cc1541fa4163a838f333419280779611
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014529"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a>Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in Skype for Business Server

Remotebenutzer sind Benutzer in Ihrer Organisation, die über eine dauerhafte Active Directory-Identität innerhalb der Organisation verfügen. Remotebenutzer melden sich häufig von außerhalb Ihres Netzwerks bei Skype for Business Server an, indem sie ein virtuelles privates Netzwerk (VPN) verwenden, wenn sie nicht mit dem Netzwerk Ihrer Organisation verbunden sind. Remotebenutzer umfassen Mitarbeiter, die zu Hause oder unterwegs arbeiten, sowie andere Remotemitarbeiter, z. B. vertrauenswürdige Anbieter, denen Unternehmensanmeldeinformationen erteilt wurden. Wenn Sie den Remotebenutzerzugriff für Remotebenutzer aktivieren, stellen unterstützte Remotebenutzer eine Verbindung über das Internet her und müssen keine VPN-Verbindung herstellen, um mit internen Benutzern über Skype for Business Server zusammenzuarbeiten.

Um den Remotebenutzerzugriff zu unterstützen, müssen Sie den Remotebenutzerzugriff aktivieren. Wenn Sie den Remotebenutzerzugriff aktivieren, aktivieren Sie ihn für Ihre gesamte Organisation. Wenn Sie später den Remotebenutzerzugriff vorübergehend oder dauerhaft verhindern möchten, können Sie ihn für Ihre Organisation deaktivieren. Verwenden Sie das Verfahren in diesem Abschnitt, um den Remotebenutzerzugriff für Ihre Organisation zu aktivieren oder zu deaktivieren.


> [!NOTE]  
> Das Aktivieren des Remotebenutzerzugriffs gibt nur an, dass Ihre Server, auf denen der Zugriffs-Edgedienst ausgeführt wird, die Kommunikation mit Remotebenutzern unterstützen. Remotebenutzer können jedoch erst an Chatnachrichten oder Konferenzen in Ihrer Organisation teilnehmen, wenn Sie mindestens eine Richtlinie zum Verwalten der Verwendung des Remotebenutzerzugriffs konfiguriert haben. Skype for Business Server Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden. Prioritätenreihenfolge für Skype for Business Server-Richtlinien: Eine Benutzerrichtlinie (größter Einfluss) hat Vorrang vor einer Standortrichtlinie, und eine Standortrichtlinie wiederum hat Vorrang vor einer globalen Richtlinie (geringster Einfluss). Dies bedeutet Folgendes: Je näher sich die Richtlinieneinstellung am betroffenen Objekt befindet, umso mehr Einfluss auf das Objekt hat sie. Ausführliche Informationen zum Konfigurieren von Richtlinien für die Verwendung des Remotebenutzerzugriffs finden Sie unter Konfigurieren von Richtlinien zum Steuern des [Remotebenutzerzugriffs in Skype for Business Server.](../external-access-policies/configure-policies-to-control-remote-user-access.md)


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>So aktivieren oder deaktivieren Sie den Remotebenutzerzugriff für Ihre Organisation

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Partnerverbund" und "Externer Zugriff"** und dann auf **"Zugriffs-Edgekonfiguration".**

4.  Klicken Sie auf der Seite **Konfiguration für Zugriffsedge** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Führen Sie im Abschnitt **Konfiguration für Zugriffsedge bearbeiten** eine der folgenden Aktionen aus:
    
    - Aktivieren Sie zum Aktivieren des Remotebenutzerzugriffs für Ihre Organisation das Kontrollkästchen **"Remotebenutzerzugriff aktivieren".**
    
    - Deaktivieren Sie zum Deaktivieren des Remotebenutzerzugriffs für Ihre Organisation das Kontrollkästchen **"Remotebenutzerzugriff aktivieren".**

6.  Klicken Sie auf **Commit ausführen**.

Damit sich Remotebenutzer bei Servern anmelden können, auf denen Skype for Business Server ausgeführt wird, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff konfigurieren, um den Remotebenutzerzugriff zu unterstützen. Ausführliche Informationen finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Remotebenutzerzugriffs in Skype for Business Server.](../external-access-policies/configure-policies-to-control-remote-user-access.md)


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren des Remotebenutzerzugriffs mithilfe Windows PowerShell Cmdlets

Der Remotebenutzerzugriff kann mithilfe von Windows PowerShell und dem cmdlet Set-CsAccessEdgeConfiguration verwaltet werden. Dieses Cmdlet kann entweder über die Skype for Business Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. 

## <a name="to-enable-remote-user-access"></a>So aktivieren Sie den Remotebenutzerzugriff

Um den Remotebenutzerzugriff zu aktivieren, legen Sie den Wert der **AllowOutsideUsers-Eigenschaft** auf "True" ($True) fest:

```powershell
Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True
```

## <a name="to-disable-remote-user-access"></a>So deaktivieren Sie den Remotebenutzerzugriff

Um den Remotebenutzerzugriff zu deaktivieren, legen Sie den Wert der **AllowOutsideUsers-Eigenschaft** auf "False" ($False) fest:

```powershell
Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False
```
