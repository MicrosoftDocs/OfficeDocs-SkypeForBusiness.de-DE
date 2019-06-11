---
title: 'Lync Server 2013: Konfigurieren von benutzerdefinierten Anwesenheitsstatus'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring custom presence states
ms:assetid: e17364a8-8b93-45fc-a614-c80e45435d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398997(v=OCS.15)
ms:contentKeyID: 48185534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12083d1895f8e5191f15b43efaf2835faecdb5ca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-custom-presence-states-in-lync-server-2013"></a>Konfigurieren von benutzerdefinierten Anwesenheitsstatus in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-01-10_

Wenn Sie benutzerdefinierte Anwesenheitsstatus in lync 2013 definieren möchten, erstellen Sie eine XML-Konfigurationsdatei für benutzerdefinierte Anwesenheitsinformationen, und geben Sie dann den Speicherort mithilfe der lync Server-Verwaltungsshell-Cmdlets **New-CSClientPolicy** oder **CSClientPolicy** mit dem Parameter ein. CustomStateURL.

Konfigurationsdateien weisen die folgenden Eigenschaften auf:

  - Benutzerdefinierte Anwesenheitsstatus können mit den Anwesenheits Indikatoren "verfügbar", "beschäftigt" und "nicht stören" konfiguriert werden.

  - Das Availability-Attribut bestimmt, welcher Anwesenheitsindikator dem Statustext des benutzerdefinierten Zustands zugeordnet ist. Im Beispiel weiter unten in diesem Thema wird der StatusText, der von zu Hause aus funktioniert, rechts neben dem grünen (verfügbaren) Anwesenheitsindikator angezeigt.

  - Die maximale Länge des Status Texts beträgt 64 Zeichen.

  - Es können maximal vier benutzerdefinierte Anwesenheitsstatus hinzugefügt werden.

  - Der CustomStateURL-Parameter gibt den Speicherort der Konfigurationsdatei an. In lync 2013 ist der SIP-Modus für höhere Sicherheit standardmäßig aktiviert, daher müssen Sie die benutzerdefinierte Anwesenheits Konfigurationsdatei auf einem Webserver speichern, auf dem HTTPS aktiviert ist. Andernfalls können lync 2013-Clients keine Verbindung herstellen. Eine gültige Adresse lautet beispielsweise `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.

<div>


> [!NOTE]  
> Obwohl es in einer Produktionsumgebung nicht empfohlen wird, können Sie eine Konfigurationsdatei testen, die sich auf einer nicht-HTTPS-Dateifreigabe befindet, indem Sie die Registrierungseinstellung EnableSIPHighSecurityMode verwenden, um den SIP-Modus für höchste Sicherheit auf dem Client zu deaktivieren. Anschließend können Sie die Registrierungseinstellung CustomStateURL verwenden, um einen nicht-HTTPS-Speicherort für die Konfigurationsdatei anzugeben. Beachten Sie, dass lync 2013 die Registrierungseinstellungen von lync 2010 ehrt, die Registrierungsstruktur jedoch aktualisiert wurde. Sie würden die Registrierungseinstellungen wie folgt erstellen: 
> <UL>
> <LI>
> <P>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</P>
> <P>Geben Sie Folgendes ein: DWORD</P>
> <P>Wertdaten: 0</P>
> <LI>
> <P>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</P>
> <P>Typ: String (REG_SZ)</P>
> <P>Werte Daten (Beispiele): file://\\lspool. Corp. contoso. com\LSFileShare\ClientConfigFolder\Presence.XML oder file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.XML</P></LI></UL>



</div>

Lokalisieren Sie Ihren benutzerdefinierten Anwesenheitsstatus, indem Sie ein oder mehrere Gebietsschema-ID-Schemas (LCID) in der XML-Konfigurationsdatei angeben. Das Beispiel weiter unten in diesem Thema zeigt die Lokalisierung in Englisch (USA) (1033), Norwegisch-Nynorsk (1044), Französisch-Frankreich (1036) und Türkisch (1055). Eine Liste der LCIDs finden Sie Untergebiets Schema-IDs, die <http://go.microsoft.com/fwlink/p/?linkid=157331>von Microsoft at zugewiesen wurden.

<div>

## <a name="to-add-custom-presence-states-to-lync-2013"></a>So fügen Sie benutzerdefinierte Anwesenheitsstatus zu lync 2013 hinzu

1.  Erstellen Sie eine XML-Konfigurationsdatei, die das Format des folgenden Beispiels verwendet:
    
        <?xml version="1.0"?>
        <customStates xmlns="http://schemas.microsoft.com/09/2009/communicator/customStates">
          <customState ID="1" availability="online">
            <activity LCID="1033">Working from Home</activity>
            <activity LCID="1044">activity 2 for 1044</activity>
            <activity LCID="1055">activity 3 for 1055</activity>
          </customState>
          <customState ID="2" availability="busy">
            <activity LCID="1033">In a Live Meeting</activity>
            <activity LCID="1036">Equivalent French String for - In a Live Meeting </activity>
          </customState>
          <customState ID="3" availability="busy">
            <activity LCID="1033">Meeting with Customer</activity>
            <activity LCID="1055">meeting with client</activity>
            <activity LCID="1036">Equivalent French String for - Meeting with Customer</activity>
          </customState>
          <customState ID="4" availability="do-not-disturb">
            <activity LCID="1033">Interviewing</activity>
          </customState>
        </customStates>

2.  Speichern Sie die XML-Konfigurationsdatei auf einem Webserver mit aktiviertem HTTPS. In diesem Beispiel wird die Datei "Presence. xml" genannt und an dem Speicherort https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xmlgespeichert.

3.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

4.  Definieren Sie in der lync Server-Verwaltungsshell den Speicherort der XML-Konfigurationsdatei mithilfe eines Befehls, der der folgenden ähnelt:
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  Verwenden Sie das Cmdlet **Grant-CSClientPolicy** , um diese neue Richtlinie Benutzern zuzuweisen.

Ausführliche Informationen finden Sie unter [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) und [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) in der Dokumentation zur lync Server-Verwaltungsshell.

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Standardmäßig aktualisiert lync Server 2013&nbsp;die Clientrichtlinien und-Einstellungen alle drei Stunden.</P>
> <LI>
> <P>Wenn Sie weiterhin Gruppenrichtlinieneinstellungen aus früheren Versionen wie CustomStateURL verwenden möchten, erkennt lync 2013 die Einstellungen, wenn Sie sich in der neuen Richtlinien Registrierungsstruktur (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync) befinden. Serverbasierte Clientrichtlinien haben jedoch Vorrang.</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

