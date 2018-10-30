---
title: Konfigurieren von benutzerdefinierten Anwesenheitsstatus
TOCTitle: Konfigurieren von benutzerdefinierten Anwesenheitsstatus
ms:assetid: e17364a8-8b93-45fc-a614-c80e45435d42
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398997(v=OCS.15)
ms:contentKeyID: 52056475
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von benutzerdefinierten Anwesenheitsstatus

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Sie können in Lync 2013 benutzerdefinierte Anwesenheitsstatus definieren. Erstellen Sie hierzu eine benutzerdefinierte Anwesenheitskonfigurationsdatei im XML-Format, und geben Sie unter Verwendung der Lync Server-Verwaltungsshell-Cmdlets **New-CSClientPolicy** oder **Set-CSClientPolicy** mit dem Parameter "CustomStateURL" den Speicherort der Datei an.

Konfigurationsdateien weisen die folgenden Eigenschaften auf:

  - Benutzerdefinierte Anwesenheitsstatus können mit den Anwesenheitssymbolen "Verfügbar", "Beschäftigt" und "Nicht stören" konfiguriert werden.

  - Das Verfügbarkeitsattribut legt fest, welches Anwesenheitssymbol dem Statustext für den benutzerdefinierten Status zugeordnet wird. Im Beispiel weiter unten in diesem Thema wird der Statustext "Working from Home" rechts neben dem grünen Anwesenheitssymbol (Verfügbar) angezeigt.

  - Die maximale Länge des Statustexts beträgt 64 Zeichen.

  - Es können maximal vier benutzerdefinierte Anwesenheitsstatus hinzugefügt werden.

  - Der CustomStateURL-Parameter gibt den Speicherort der Konfigurationsdatei an. In Lync 2013 ist der hohe SIP-Sicherheitsmodus standardmäßig aktiviert. Daher müssen Sie die benutzerdefinierte Anwesenheitskonfigurationsdatei auf einem Webserver speichern, auf dem HTTPS aktiviert ist. Andernfalls können Lync 2013-Clients keine Verbindung mit dem Server herstellen. Beispiel für eine gültige Adresse:`https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.


> [!NOTE]
> Sie können eine Konfigurationsdatei testen, die sich auf einer Nicht-HTTPS-Dateifreigabe befindet, indem Sie den hohen SIP-Sicherheitsmodus auf dem Client mit der Registrierungseinstellung "EnableSIPHighSecurityMode" deaktivieren. In einer Produktionsumgebung wird aber davon abgeraten. Dann können Sie mit der Registrierungseinstellung "CustomStateURL" einen Nicht-HTTPS-Speicherort für die Konfigurationsdatei angeben. Beachten Sie, dass Lync 2013 die Lync 2010-Registrierungseinstellungen berücksichtigt, aber die Registrierungsstruktur wurde aktualisiert. Die Registrierungseinstellungen werden wie folgt erstellt: 
> <UL>
> <LI>
> <P>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</P>
> <P>Typ: DWORD</P>
> <P>Wertdaten: 0</P>
> <LI>
> <P>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</P>
> <P>Typ: Zeichenfolge (REG_SZ)</P>
> <P>Wertdaten (Beispiele): file://\\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml oder file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</P></LI></UL>



Sie können eine Übersetzung Ihrer benutzerdefinierten Anwesenheitsstatus bereitstellen, indem Sie eine oder mehrere Gebietsschema-IDs in Ihrer XML-Konfigurationsdatei angeben. Das Beispiel weiter unten in diesem Thema zeigt die Übersetzung in Englisch – USA (1033), Norwegisch – Bokmål (1044), Französisch – Frankreich (1036) und Türkisch (1055). Eine Liste der Gebietsschema-IDs finden Sie auf der Seite "Von Microsoft zugewiesene Gebietsschema-IDs" unter <http://go.microsoft.com/fwlink/?linkid=157331>.

## So fügen Sie in Lync 2013 benutzerdefinierte Anwesenheitsstatus hinzu

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

2.  Speichern Sie die XML-Konfigurationsdatei auf einem Webserver, auf dem HTTPS aktiviert ist. In diesem Beispiel hat die Datei den Namen "Presence.xml" und wird an dem Speicherort "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml" gespeichert.

3.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

4.  Definieren Sie in der Lync Server-Verwaltungsshell den Speicherort Ihrer XML-Konfigurationsdatei mit einem Befehl, der dem folgenden ähnelt:
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  Verwenden Sie das Cmdlet **Grant-CSClientPolicy**, um diese neue Richtlinie Benutzern zuzuweisen.

Ausführliche Informationen finden Sie unter [New-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientPolicy) und [Grant-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsClientPolicy) in der Lync Server-Verwaltungsshell-Dokumentation.


> [!NOTE]
> <UL>
> <LI>
> <P>Standardmäßig aktualisiert Lync Server 2013 die Clientrichtlinien und -einstellungen alle drei Stunden.</P>
> <LI>
> <P>Wenn Sie weiterhin die Gruppenrichtlinieneinstellungen aus vorherigen Versionen verwenden möchten, z.&nbsp;B. "CustomStateURL", werden die Einstellungen von Lync 2013 erkannt, wenn diese sich in der neuen Registrierungsstruktur für Richtlinien (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync) befinden. Allerdings haben serverbasierte Clientrichtlinien Vorrang.</P></LI></UL>


