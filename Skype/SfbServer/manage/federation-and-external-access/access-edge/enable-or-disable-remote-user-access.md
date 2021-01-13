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
localization_priority: Normal
description: Wenn Sie den Remotebenutzerzugriff für Remotebenutzer aktivieren, stellen unterstützte Remotebenutzer eine Verbindung über das Internet und müssen keine Verbindung über ein VPN herstellen, um mit internen Benutzern über Skype for Business Server zusammenzuarbeiten.
ms.openlocfilehash: 9e5ba5828e129c6fed5dd892b1a7bb8e6bd64707
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817395"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a>Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in Skype for Business Server

Remotebenutzer sind Benutzer in Ihrer Organisation, die über eine dauerhafte Active Directory-Identität innerhalb der Organisation verfügen. Remotebenutzer melden sich häufig von außerhalb Ihres Netzwerks über ein virtuelles privates Netzwerk (VPN) bei Skype for Business Server an, wenn sie nicht mit dem Netzwerk Ihrer Organisation verbunden sind. Remotebenutzer sind Mitarbeiter, die zu Hause oder unterwegs arbeiten, und andere Remotemitarbeiter, z. B. vertrauenswürdige Anbieter, denen Unternehmensanmeldeinformationen erteilt wurden. Wenn Sie den Remotebenutzerzugriff für Remotebenutzer aktivieren, stellen unterstützte Remotebenutzer eine Verbindung über das Internet und müssen keine Verbindung über ein VPN herstellen, um mit internen Benutzern über Skype for Business Server zusammenzuarbeiten.

Um den Zugriff durch Remotebenutzer zu unterstützen, müssen Sie den Remotebenutzerzugriff aktivieren. Wenn Sie den Remotebenutzerzugriff aktivieren, aktivieren Sie ihn für die gesamte Organisation. Wenn Sie später den Zugriff durch Remotebenutzer vorübergehend oder dauerhaft verhindern möchten, können Sie ihn für Ihre Organisation deaktivieren. Verwenden Sie das Verfahren in diesem Abschnitt, um den Remotebenutzerzugriff für Ihre Organisation zu aktivieren oder zu deaktivieren.


> [!NOTE]  
> Das Aktivieren des Zugriffs durch Remotebenutzer gibt nur an, dass die Server, auf denen der Zugriffs-Edgedienst ausgeführt wird, die Kommunikation mit Remotebenutzern unterstützen, Remotebenutzer können jedoch erst an Sofortnachrichten oder Konferenzen in Ihrer Organisation teilnehmen, wenn Sie auch mindestens eine Richtlinie für die Verwaltung der Verwendung des Remotebenutzerzugriffs konfigurieren. Skype for Business Server-Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden. Prioritätenreihenfolge für Skype for Business Server-Richtlinien: Eine Benutzerrichtlinie (größter Einfluss) hat Vorrang vor einer Standortrichtlinie, und eine Standortrichtlinie wiederum hat Vorrang vor einer globalen Richtlinie (geringster Einfluss). Dies bedeutet Folgendes: Je näher sich die Richtlinieneinstellung am betroffenen Objekt befindet, umso mehr Einfluss auf das Objekt hat sie. Weitere Informationen zum Konfigurieren von Richtlinien für die Verwendung des Remotebenutzerzugriffs finden Sie unter "Konfigurieren von Richtlinien zur Steuerung des [Remotebenutzerzugriffs in Skype for Business Server".](../external-access-policies/configure-policies-to-control-remote-user-access.md)


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>So aktivieren oder deaktivieren Sie den Remotebenutzerzugriff für Ihre Organisation

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Verbund" und**"Externer Zugriff" und dann auf **"Zugriffs-Edgekonfiguration".**

4.  Klicken Sie auf der Seite **Konfiguration für Zugriffsedge** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Führen Sie im Abschnitt **Konfiguration für Zugriffsedge bearbeiten** eine der folgenden Aktionen aus:
    
      - Aktivieren Sie das Kontrollkästchen "Remotebenutzerzugriff aktivieren", um den Remotebenutzerzugriff für Ihre **Organisation** zu aktivieren.
    
      - Deaktivieren Sie das Kontrollkästchen "Remotebenutzerzugriff aktivieren", um den Remotebenutzerzugriff für Ihre **Organisation** zu deaktivieren.

6.  Klicken Sie auf **Commit ausführen**.

Damit sich Remotebenutzer bei Ihren Servern mit Skype for Business Server anmelden können, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff konfigurieren, um den Zugriff durch Remotebenutzer zu unterstützen. Weitere Informationen finden Sie unter ["Konfigurieren von Richtlinien zum Steuern des Remotebenutzerzugriffs in Skype for Business Server".](../external-access-policies/configure-policies-to-control-remote-user-access.md)


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren des Remotebenutzerzugriffs mithilfe Windows PowerShell Cmdlets

Der Zugriff durch Remotebenutzer kann mithilfe von Windows PowerShell und dem Set-CsAccessEdgeConfiguration verwaltet werden. Dieses Cmdlet kann entweder über die Skype for Business Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell. 

## <a name="to-enable-remote-user-access"></a>So aktivieren Sie den Remotebenutzerzugriff

  - Um den Zugriff durch Remotebenutzer zu aktivieren, legen Sie den Wert der **Eigenschaft "AllowOutsideUsers"** auf "True" ($True) $True:
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a>So deaktivieren Sie den Zugriff durch Remotebenutzer

  - Um den Zugriff durch Remotebenutzer zu deaktivieren, legen Sie den Wert der **Eigenschaft "AllowOutsideUsers"** auf "False" ($False):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


