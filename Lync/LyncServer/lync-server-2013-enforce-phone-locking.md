---
title: 'Lync Server 2013: Erzwingen der Telefonsperre'
description: 'Lync Server 2013: erzwingen Sie die Telefonsperre.'
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
ms.openlocfilehash: 5afae4fa27edf9378bacc39a29697c9607b25c07
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575601"
---
# <a name="enforce-phone-locking-in-lync-server-2013"></a>Erzwingen der Telefonsperre in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Lync Phone Edition-Geräte können aus Sicherheitsgründen gesperrt werden. Wenn Sie die Telefonsperre erzwingen, sperrt das Gerät, auf dem lync installiert ist, Phone Edition nach einer von Ihnen konfigurierten Zeitspanne. Wenn ein Telefon gesperrt ist, kann ein Benutzer Anrufe tätigen, aber nicht auf Kalender-und Kontaktinformationen, Voicemails oder Anrufprotokolle zugreifen oder die Suche verwenden. Um das Telefon zu entsperren, gibt der Benutzer eine PIN ein.

Um die Telefonsperre zu erzwingen, aktivieren und konfigurieren Sie Sie mithilfe von lync Server-Systemsteuerung oder lync Server PowerShell-Cmdlets. Sie können die Telefonsperre Global oder nur innerhalb der Website erzwingen, für die Sie konfiguriert ist.

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a>So konfigurieren und erzwingen Sie die Telefonsperre

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf **Clients** und anschließend auf **Gerätekonfiguration**.

4.  Doppelklicken Sie auf der Registerkarte **Gerätekonfiguration** in der Liste der Gerätekonfigurationen auf diejenige Konfiguration, deren Einstellungen für die Telefonsperre Sie ändern möchten.

5.  Stellen Sie im Dialogfeld **Gerätekonfiguration bearbeiten** sicher, dass das Kontrollkästchen **Gerätesperre erzwingen** aktiviert ist.

6.  Übernehmen Sie in der **minimalen PIN-Länge**den Standardwert für die minimale Anzahl von stellen, die die Unlock-Pin enthalten muss, oder geben Sie einen neuen Wert an. Der Bereich für die PIN-Länge beträgt vier bis 15 Ziffern, der Standardwert ist 6.

7.  Übernehmen Sie im **Telefon Sperrtimeout**den Standardwert für die minimale Zeitdauer, bevor das Telefon sich selbst sperrt, oder geben Sie einen neuen Wert ein. Der Bereich für das Timeout ist 0 bis 60 Minuten, und der Standardwert ist 10. Geben Sie den Wert im Format HH:MM:SS ein.

8.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a>Erzwingen der Telefonsperre mithilfe von Windows PowerShell-Cmdlets

Die Telefonsperre kann mithilfe des Set-CsUCPhoneConfiguration-Cmdlets erzwungen werden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-enable-phone-locking"></a>So aktivieren Sie die Telefonsperre

  - Mit dem folgenden Befehl können Sie die Telefonsperre für den Standort Redmond aktivieren. Setzen Sie zum Deaktivieren der Telefonsperre die Eigenschaft "EnforcePhoneLock" auf "False" ($False).
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a>So aktivieren Sie das Sperren von Telefon sperren und Ändern des Timeouts für die Telefonsperre

  - Mit diesem Befehl wird die Telefonsperre aktiviert und das Timeout für die Telefonsperre auf 30 Minuten festgelegt.
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a>So aktivieren Sie die Telefonsperre in der gesamten Organisation

  - In diesem Beispiel ist die Telefonsperre für alle in der Organisation eingesetzten UC-Telefonkonfigurationseinstellungen aktiviert.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) ".

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Verwalten der lync Server 2013 Authentifizierung](lync-server-2013-managing-lync-server-authentication.md)  


[Verwalten von Geräten, Telefonen und Clientanwendungen in lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

