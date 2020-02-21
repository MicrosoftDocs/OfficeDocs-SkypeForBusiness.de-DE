---
title: Ändern der Standardaktion für Clients, die nicht explizit unterstützt oder eingeschränkt sind
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default action for clients not explicitly supported or restricted
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520994(v=OCS.15)
ms:contentKeyID: 48184137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87f2b88b43c41a5a8bf990a72f0fdfef1c5537e2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a>Ändern Sie die Standardaktion für Clients, die nicht explizit unterstützt oder in lync Server 2013 eingeschränkt sind.

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Zusätzlich zur Angabe der Version der Clients, die Sie in ihrer lync Server 2013 Umgebung unterstützen möchten, können Sie auch eine Standardaktion für Clients angeben, für die noch keine Versionsrichtlinie definiert ist. Auf diese Weise können Sie einschränken, welche Clientversionen in ihrer lync Server Umgebung verwendet werden, was Ihnen helfen kann, die mit der Unterstützung mehrerer Clientversionen verbundenen Kosten zu steuern.

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a>So ändern Sie die Standardaktion für Clients, die nicht explizit unterstützt oder eingeschränkt werden

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf **Clientversionskonfiguration**.

4.  Doppelklicken Sie auf der Seite **Clientversionskonfiguration** auf die Konfiguration **Global** in der Liste.

5.  Stellen Sie im Dialogfeld **Clientversionskonfiguration bearbeiten** sicher, dass das Kontrollkästchen **Versionskontrolle aktivieren** aktiviert ist, und wählen Sie anschließend unter **Standardaktion** eine der folgenden Optionen aus:
    
      - **Allow**   ermöglicht dem Client die Anmeldung, wenn die Client Version keinem Filter in der Liste mit den **clientversionsrichtlinien** entspricht.
    
      - **Blockieren**   verhindert, dass der Client sich anmeldet, wenn die Client Version keinem Filter in der Liste mit den **clientversionsrichtlinien** entspricht.
    
      - **Blockieren mit URL**   verhindert, dass der Client sich anmeldet, wenn die Client Version keinem Filter in der Liste mit den **clientversionsrichtlinien** entspricht, und eine Fehlermeldung mit einer URL enthält, in der ein neuerer Client heruntergeladen werden kann.
    
      - **Allow with URL**   ermöglicht dem Client die Anmeldung, wenn die Client Version keinem Filter in der Liste mit den **clientversionsrichtlinien** entspricht, und eine Fehlermeldung mit einer URL enthält, in der ein neuerer Client heruntergeladen werden kann.

6.  Wenn Sie die Option **Blockieren mit URL** auswählen, geben Sie im Feld **URL** die URL für den Clientdownload ein, die in der Fehlermeldung angezeigt werden soll.

7.  Klicken Sie auf **Commit**.

</div>

<div>

## <a name="to-disable-client-version-control"></a>So deaktivieren Sie die Clientversionskontrolle

  - Um die Versionskontrolle zu deaktivieren und allen Clients unabhängig von der Clientversion die Anmeldung zu ermöglichen, deaktivieren Sie das Kontrollkästchen **Versionskontrolle aktivieren**, und klicken Sie anschließend auf **Commit**.

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a>Ändern der Standardaktion mithilfe von Windows PowerShell-Cmdlets

Die Standardaktion, die ausgeführt werden soll, wenn Benutzer versuchen, sich mit Clients zu anmelden, die nicht explizit unterstützt oder durch eine clientversionsrichtlinie eingeschränkt sind, können über Windows PowerShell Befehlszeilenschnittstelle und das Cmdlet " **CsClientVersionPolicy** " verwaltet werden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

<div>

## <a name="to-configure-the-default-action-to-block-access"></a>So konfigurieren Sie die Standardaktion zum Blockieren des Zugriffs

  - Mit dem folgenden Befehl wird die Standardaktion zum Blockieren des Standorts "Redmond" festgelegt. Dadurch wird die Registrierung für alle Clients blockiert, für die keine Konfigurationsregel bezüglich der Clientversion vorhanden ist.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a>So konfigurieren Sie die Standardaktion zum Zulassen des Zugriffs

  - In diesem Beispiel ist die Standardaktion für den Standort "Redmond" auf "Zulassen" festgelegt. Dadurch wird die Registrierung für alle Clients zugelassen, für die keine Konfigurationsregel bezüglich der Clientversion vorhanden ist.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet " [CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15)) ".

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Verwalten von Geräten, Telefonen und Clientanwendungen in lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

