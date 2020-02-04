---
title: 'Lync Server 2013: Erzwingen der Telefon Sperrung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enforce phone locking
ms:assetid: 1f89298b-aea9-4952-93ca-0270b565792b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520963(v=OCS.15)
ms:contentKeyID: 48183594
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c781c09db1834d85a1df4532d1484e43d74ca48
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enforce-phone-locking-in-lync-server-2013"></a>Erzwingen der Telefon Sperrung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Lync Phone Edition-Geräte können aus Sicherheitsgründen gesperrt werden. Wenn Sie die Telefonsperre erzwingen, sperrt das Gerät, auf dem lync Phone Edition ausgeführt wird, nach einer von Ihnen konfigurierten Zeitspanne. Wenn ein Telefon gesperrt ist, kann ein Benutzer Anrufe tätigen, kann aber nicht auf Kalender-und Kontaktinformationen, Voicemail oder Anrufprotokolle zugreifen oder die Suchfunktion verwenden. Um das Telefon zu entsperren, gibt der Benutzer eine PIN ein.

Wenn Sie die Telefonsperre erzwingen möchten, aktivieren und konfigurieren Sie Sie mithilfe der lync Server Control Panel-oder lync Server PowerShell-Cmdlets. Sie können die Telefonsperre Global oder nur innerhalb der Website erzwingen, für die Sie konfiguriert ist.

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a>So konfigurieren und erzwingen Sie die Telefonsperre

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf **Clients**, und klicken Sie dann auf **Gerätekonfiguration**.

4.  Doppelklicken Sie auf der Registerkarte **Gerätekonfiguration** in der Liste der Gerätekonfigurationen auf die Konfiguration, für die Sie die Einstellungen für die Telefonsperre ändern möchten.

5.  Überprüfen Sie im Dialogfeld **Gerätekonfiguration bearbeiten** , ob das Kontrollkästchen **Gerätesperrung erzwingen** aktiviert ist.

6.  Übernehmen Sie in **minimaler PIN-Länge**den Standardwert für die Mindestanzahl von stellen, die die Unlock-Pin enthalten muss, oder geben Sie einen neuen Wert an. Der Bereich für die PIN-Länge beträgt vier bis fünfzehn Ziffern, der Standardwert ist 6.

7.  Über **nehmen Sie den**Standardwert für die Mindestzeitdauer, bevor das Telefon sich selbst sperrt, oder geben Sie einen neuen Wert an. Der Bereich für das Timeout beträgt 0 bis 60 Minuten, und der Standardwert ist 10. Geben Sie den Wert im Format HH:MM:SS ein.

8.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a>Erzwingen der Telefon Sperrung mithilfe von Windows PowerShell-Cmdlets

Das Sperren von Telefonen kann mithilfe des Cmdlets "CsUCPhoneConfiguration" erzwungen werden. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-enable-phone-locking"></a>So aktivieren Sie die Telefon Sperrung

  - Mit dem folgenden Befehl wird die Telefon Sperrung für die Redmond-Website aktiviert. Um die Telefon Sperrung zu deaktivieren, setzen Sie die EnforcePhoneLock-Eigenschaft auf false ($false).
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a>So aktivieren Sie das Sperren von Telefonen und Ändern des Timeouts für Telefon sperren

  - Dieser Befehl ermöglicht das Sperren von Telefonen und legt das Timeout für die Telefonsperre auf 30 Minuten fest.
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a>So aktivieren Sie die Telefon Sperrung in der gesamten Organisation

  - In diesem Beispiel ist die Telefon Sperrung für alle UC-Telefon Konfigurationseinstellungen aktiviert, die in der Organisation verwendet werden.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) ".

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Verwalten der lync Server 2013-Authentifizierung](lync-server-2013-managing-lync-server-authentication.md)  


[Verwalten von Geräten, Telefonen und Clientanwendungen in Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

