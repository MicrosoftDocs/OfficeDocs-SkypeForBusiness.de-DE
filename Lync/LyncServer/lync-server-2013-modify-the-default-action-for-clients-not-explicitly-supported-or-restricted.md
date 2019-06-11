---
title: Ändern der Standardaktion für nicht explizit unterstützte oder eingeschränkte Clients
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the default action for clients not explicitly supported or restricted
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520994(v=OCS.15)
ms:contentKeyID: 48184137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97b364253a87f1cbff1ef60322c65780b6497880
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a>Ändern der Standardaktion für Clients, die in lync Server 2013 nicht explizit unterstützt oder eingeschränkt werden

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Sie können nicht nur die Version der Clients angeben, die Sie in ihrer lync Server 2013-Umgebung unterstützen möchten, sondern auch eine Standardaktion für Clients angeben, für die noch keine Versionsrichtlinie definiert ist. Auf diese Weise können Sie einschränken, welche Clientversionen in ihrer lync Server-Umgebung verwendet werden, was Ihnen helfen kann, die Kosten zu kontrollieren, die mit der Unterstützung mehrerer Clientversionen verbunden sind.

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a>So ändern Sie die Standardaktion für nicht explizit unterstützte oder eingeschränkte Clients

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf **Client Versions Konfiguration**.

4.  Doppelklicken Sie auf der Seite **Client Versions Konfiguration** auf die **globale** Konfiguration in der Liste.

5.  Überprüfen Sie im Dialogfeld **Client-Versions Konfiguration bearbeiten** , ob das Kontrollkästchen **Versionskontrolle aktivieren** aktiviert ist, und wählen Sie dann unter **Standardaktion**eine der folgenden Optionen aus:
    
      - **Zulassen**   ermöglicht es dem Client, sich anzumelden, wenn die Client Version nicht mit einem Filter in der Liste der **clientversionsrichtlinien** übereinstimmt.
    
      - **Blockieren**   verhindert, dass der Client sich anmeldet, wenn die Client Version keinem Filter in der Liste der **clientversionsrichtlinien** entspricht.
    
      - **Blockieren mit URL**   verhindert, dass der Client sich anmeldet, wenn die Client Version keinem Filter in der Liste der **clientversionsrichtlinien** entspricht und eine Fehlermeldung mit einer URL enthält, in der ein neuerer Client heruntergeladen werden kann.
    
      - **Allow with URL**   ermöglicht es dem Client, sich anzumelden, wenn die Client Version keinem Filter in der Liste der **clientversionsrichtlinien** entspricht und eine Fehlermeldung mit einer URL enthält, in der ein neuerer Client heruntergeladen werden kann.

6.  Wenn Sie **Block with URL**ausgewählt haben, geben Sie die Client Download-URL ein, die in die Fehlermeldung im Feld **URL** eingeschlossen werden soll.

7.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="to-disable-client-version-control"></a>So deaktivieren Sie die Client Versionskontrolle

  - Wenn Sie die Versionskontrolle deaktivieren möchten, damit sich alle Clients unabhängig von der Client Version anmelden können, deaktivieren Sie das Kontrollkästchen **Versionskontrolle aktivieren** , und klicken Sie dann auf **Commit**.

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a>Ändern der Standardaktion mithilfe von Windows PowerShell-Cmdlets

Die Standardaktion, die ausgeführt werden soll, wenn Benutzer versuchen, sich mithilfe von Clients anzuschließen, die nicht explizit unterstützt werden oder durch eine clientversionsrichtlinie eingeschränkt sind, können mithilfe der Windows PowerShell-Befehlszeilenschnittstelle und des Cmdlets " **CsClientVersionPolicy** " verwaltet werden. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-configure-the-default-action-to-block-access"></a>So konfigurieren Sie die Standardaktion zum Blockieren des Zugriffs

  - Mit dem folgenden Befehl wird die Standardaktion für den Redmond-Website Block festgelegt. Dadurch wird die Registrierung für jeden Client blockiert, für den keine Client-Versions Konfigurationsregel vorhanden ist.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a>So konfigurieren Sie die Standardaktion zum Zulassen des Zugriffs

  - In diesem Beispiel ist die Standardaktion für die Website "Redmond" auf "zulassen" eingestellt. Dies ermöglicht die Registrierung für jeden Client, für den keine Client-Versions Konfigurationsregel vorhanden ist.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15)) ".

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Verwalten von Geräten, Telefonen und Clientanwendungen in Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

