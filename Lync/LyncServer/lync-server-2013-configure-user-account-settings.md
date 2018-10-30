---
title: 'Lync Server 2013: Konfigurieren der Benutzerkontoeinstellungen '
TOCTitle: 'Konfigurieren der Benutzerkontoeinstellungen '
ms:assetid: b7c74ecc-b924-4efc-8a56-3a5f94a9ef13
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412896(v=OCS.15)
ms:contentKeyID: 49295184
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der Benutzerkontoeinstellungen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Teilnehmer an Einwahlkonferenzen geben ihre Telefonnummer oder Durchwahl sowie eine PIN ein, um als authentifizierte Benutzer an Konferenzen teilzunehmen. Der für Lync Server-Benutzerkonten angegebenen **Anschluss-URI** ist für die Authentifizierung erforderlich.

In diesem Thema wird beschrieben, wie Sie einem einzelnen Benutzerkonto einen **Anschluss-URI** zuweisen. Wenn Sie einen **Anschluss-URI** für mehrere Benutzerkonten zuweisen müssen, können Sie ein Skript erstellen, das auf das **Set-CsUser**-Cmdlet zugreift. Genauere Informationen zur Verwendung eines Beispielskripts für die Zuweisung eines **Anschluss-URIs** zu mehreren Benutzerkonten finden Sie unter "Assign Line URIs to Multiple Users" unter [http://go.microsoft.com/fwlink/p/?linkId=196945](http://go.microsoft.com/fwlink/p/?linkid=196945).

## So konfigurieren Sie die Benutzerkontoeinstellungen

1.  Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle **Cs-UserAdministrator** oder **CsAdministrator** an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer** .

4.  Geben Sie in das Suchfeld den Namen des Benutzers ein, den Sie für Einwahlkonferenzen konfigurieren möchten, oder klicken Sie auf **Filter hinzufügen** , um Suchfelder anzugeben, und klicken Sie dann auf **Suchen** .

5.  Doppelklicken Sie auf den Benutzernamen, um das Dialogfeld **Lync Server-Benutzer bearbeiten** zu öffnen.

6.  Geben Sie unter **Telefonie** in das Feld **Anschluss-URI** eine eindeutige, normalisierte Telefonnumer ein (beispielsweise tel:+14255550200).
    

    > [!NOTE]
    > Sie können <STRONG>Anschluss-URI</STRONG> nur angeben, wenn <STRONG>Telefonie</STRONG> auf <STRONG>Nur von PC zu PC</STRONG> , <STRONG>Enterprise-VoIP</STRONG> , <STRONG>Remoteanrufsteuerung</STRONG> oder <STRONG>Nur Remoteanrufsteuerung</STRONG> festgelegt ist.



7.  Klicken Sie auf **Commit** .

