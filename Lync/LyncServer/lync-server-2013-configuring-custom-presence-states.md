---
title: 'Lync Server 2013: Konfigurieren von benutzerdefinierten Anwesenheitsstatus'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring custom presence states
ms:assetid: e17364a8-8b93-45fc-a614-c80e45435d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398997(v=OCS.15)
ms:contentKeyID: 48185534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f93229ee06a3d45db2478003a18ac22a2e7cf59
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203101"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-custom-presence-states-in-lync-server-2013"></a>Konfigurieren von benutzerdefinierten Anwesenheitsstatus in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-01-10_

Um benutzerdefinierte Anwesenheitsstatus in lync 2013 zu definieren, erstellen Sie eine XML-benutzerdefinierte Anwesenheits Konfigurationsdatei, und geben Sie dann den Speicherort mithilfe lync Server-Verwaltungsshell der Cmdlets **New-CSClientPolicy** oder **CSClientPolicy** mit dem Parameter CustomStateURL an.

Konfigurationsdateien weisen die folgenden Eigenschaften auf:

  - Benutzerdefinierte Anwesenheitsstatus können mit den Anwesenheitssymbolen "Verfügbar", "Beschäftigt" und "Nicht stören" konfiguriert werden.

  - Das Verfügbarkeitsattribut legt fest, welches Anwesenheitssymbol dem Statustext für den benutzerdefinierten Status zugeordnet wird. Im Beispiel weiter unten in diesem Thema wird der StatusText, der von zu Hause aus funktioniert, rechts neben dem Grün (verfügbar) Anwesenheitssymbol angezeigt.

  - Die maximale Länge des Statustexts beträgt 64 Zeichen.

  - Es können maximal vier benutzerdefinierte Anwesenheitsstatus hinzugefügt werden.

  - Der Parameter CustomStateURL gibt den Speicherort der Konfigurationsdatei an. In lync 2013 ist der SIP-Modus für hohe Sicherheit standardmäßig aktiviert, sodass Sie die benutzerdefinierte Anwesenheits Konfigurationsdatei auf einem Webserver speichern müssen, auf dem HTTPS aktiviert ist. Andernfalls können lync 2013 Clients keine Verbindung dazu herstellen. Beispielsweise wäre eine gültige Adresse `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.

<div>


> [!NOTE]  
> Obwohl es in einer Produktionsumgebung nicht empfohlen wird, können Sie eine Konfigurationsdatei testen, die sich auf einer nicht-HTTPS-Dateifreigabe befindet, indem Sie die Registrierungseinstellung EnableSIPHighSecurityMode verwenden, um den SIP-Modus für hohe Sicherheit auf dem Client zu deaktivieren. Anschließend können Sie die Registrierungseinstellung CustomStateURL verwenden, um einen nicht-HTTPS-Speicherort für die Konfigurationsdatei anzugeben. Beachten Sie, dass lync 2013 lync 2010 Registrierungseinstellungen ehrt, die Registrierungsstruktur jedoch aktualisiert wurde. Sie würden die Registrierungseinstellungen wie folgt erstellen: 
> <UL>
> <LI>
> <P>HKEY_LOCAL_MACHINE \software\policies\microsoft\office\15.0\lync\enablesiphighsecuritymode</P>
> <P>Typ: DWORD</P>
> <P>Wertdaten: 0</P>
> <LI>
> <P>HKEY_LOCAL_MACHINE \software\policies\microsoft\office\15.0\lync\customstateurl</P>
> <P>Typ: String (REG_SZ)</P>
> <P>Werte Daten (Beispiele): file://\\lspool. Corp. contoso. com\LSFileShare\ClientConfigFolder\Presence.XML oder file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.XML</P></LI></UL>



</div>

Sie können eine Übersetzung Ihrer benutzerdefinierten Anwesenheitsstatus bereitstellen, indem Sie eine oder mehrere Gebietsschema-IDs in Ihrer XML-Konfigurationsdatei angeben. Das Beispiel weiter unten in diesem Thema zeigt die Übersetzung in Englisch – USA (1033), Norwegisch – Bokmål (1044), Französisch – Frankreich (1036) und Türkisch (1055). Eine Liste der LCIDs finden Sie Untergebiets Schema-IDs, die <https://go.microsoft.com/fwlink/p/?linkid=157331>von Microsoft unter zugewiesen wurden.

<div>

## <a name="to-add-custom-presence-states-to-lync-2013"></a>So fügen Sie lync 2013 benutzerdefinierte Anwesenheitsstatus hinzu

1.  Erstellen Sie eine XML-Konfigurationsdatei, die das im folgenden Beispiel gezeigte Format verwendet:
    
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

2.  Speichern Sie die XML-Konfigurationsdatei auf einem Webserver mit aktiviertem HTTPS. In diesem Beispiel wird die Datei Presence. xml genannt und im Speicherort https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xmlgespeichert.

3.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

4.  Definieren Sie in der lync Server-Verwaltungsshell den Speicherort der XML-Konfigurationsdatei mithilfe eines Befehls wie den folgenden:
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  Verwenden Sie das **Grant-CSClientPolicy-** Cmdlet, um diese neue Richtlinie Benutzern zuzuweisen.

Ausführliche Informationen finden Sie unter [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) und [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) in der lync Server-Verwaltungsshell Dokumentation.

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Standardmäßig aktualisiert lync Server 2013&nbsp;alle drei Stunden Clientrichtlinien und-Einstellungen.</P>
> <LI>
> <P>Wenn Sie weiterhin Gruppenrichtlinieneinstellungen aus früheren Versionen wie CustomStateURL verwenden möchten, werden lync 2013 die Einstellungen erkennen, wenn Sie sich in der neuen Registrierungsstruktur der Richtlinie befinden (HKEY_LOCAL_MACHINE \software\policies\microsoft\office\15.0\lync). Allerdings haben serverbasierte Clientrichtlinien Vorrang.</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

