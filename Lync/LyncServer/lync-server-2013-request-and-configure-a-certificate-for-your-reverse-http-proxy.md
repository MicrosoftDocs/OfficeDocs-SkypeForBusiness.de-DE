---
title: Anfordern und Konfigurieren eines Zertifikats für den HTTP-Reverseproxy
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request and configure a certificate for your reverse HTTP proxy
ms:assetid: 4b70991e-5f10-40a3-b069-0b227c3a3a0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429704(v=OCS.15)
ms:contentKeyID: 48184085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2597bf31c9f0cc9f4316f505811426f2c9948a6f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723850"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a>Anfordern und Konfigurieren eines Zertifikats für den HTTP-Reverseproxy in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-02-14_

Sie müssen das Zertifikat der Stammzertifizierungsstelle auf dem Server mit Microsoft Forefront Threat Management Gateway 2010 oder IIS arr für die Zertifizierungsstellen-Infrastruktur installieren, die die Serverzertifikate für die internen Server mit Microsoft lync ausgestellt hat. Server 2013.

Sie müssen auch ein öffentliches Webserverzertifikat auf dem Reverse Proxy Server installieren. Die alternativen Namen dieses Zertifikats sollten die veröffentlichten externen vollqualifizierten Domänennamen (FQDNs) der einzelnen Pools enthalten, die für Remotezugriff aktivierte Benutzer sind, und die externen FQDNs aller Directors-oder Director-Pools, die innerhalb von verwendet werden. Diese Edge-Infrastruktur. Der Alternative Name des Antragstellers muss auch die einfache URL der Besprechung, die einfache URL für Einwahl und, wenn Sie Mobile Anwendungen bereitstellen und die automatische Ermittlung verwenden möchten, die URL des externen AutoErmittlungsdiensts enthalten, wie in der folgenden Tabelle dargestellt.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Wert</th>
<th>Beispiel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name des Antragstellers</p></td>
<td><p>Pool-FQDN</p></td>
<td><p>webext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Alternativer Antragstellername</p></td>
<td><p>Pool-FQDN</p></td>
<td><p>webext.contoso.com</p>



> [!IMPORTANT]
> Der Name des Antragstellers muss auch im alternativen Betreff vorhanden sein.

</td>
</tr>
<tr class="odd">
<td><p>Alternativer Antragstellername</p></td>
<td><p>Optionale Director-Webdienste (wenn Director bereitgestellt wird)</p></td>
<td><p>webdirext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Alternativer Antragstellername</p></td>
<td><p>Einfache URL für Besprechungen</p>



> [!NOTE]
> Alle einfachen URLs der Besprechung müssen dem alternativen Betreff Namen entsprechen. Für jede SIP-Domäne muss mindestens eine einfache URL für die aktive Besprechung vorhanden sein.

</td>
<td><p>meet.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>Alternativer Antragstellername</p></td>
<td><p>Einfache URLs vom Typ „Dialin“</p></td>
<td><p>dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Alternativer Antragstellername</p></td>
<td><p>Office Web Apps-Server</p></td>
<td><p>officewebapps01.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>Alternativer Antragstellername</p></td>
<td><p>URL des externen AutoErmittlungsdiensts</p></td>
<td><p>lyncdiscover.contoso.com</p>



> [!NOTE]
> Wenn Sie auch Microsoft Exchange Server verwenden, müssen Sie auch Reverse-Proxy Regeln für die Exchange-Auto Ermittlungs-und Webdienste-URLs konfigurieren.

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> Wenn Ihre interne Bereitstellung aus mehreren Standard Edition-Servern oder Front-End-Pools besteht, müssen Sie Webveröffentlichungsregeln für jeden FQDN der externen Webfarm konfigurieren, und Sie benötigen entweder ein Zertifikat und einen Weblistener für jede Person, oder Sie müssen ein Zertifikat anfordern. dessen Betreff-Alternative Name die von allen Pools verwendeten Namen enthält, weisen Sie ihn einem Weblistener zu, und geben Sie ihn unter mehreren Webveröffentlichungsregeln frei.



</div>

<div>

## <a name="create-a-certificate-request"></a>Erstellen einer Zertifikatanforderung

Sie erstellen eine Zertifikatanforderung auf dem Reverse-Proxy. Wenn Sie eine Anforderung auf einem anderen Computer erstellen, müssen Sie das signierte Zertifikat mit dem privaten Schlüssel exportieren und dann auf den Reverseproxy importieren, nachdem Sie es von der öffentlichen Zertifizierungsstelle erhalten haben.

<div>


> [!NOTE]
> Eine Zertifikatanforderung oder eine Zertifikatsignaturanforderung (CSR) ist eine Anforderung an eine vertrauenswürdige öffentliche Zertifizierungsstelle, um den öffentlichen Schlüssel des anfordernden Computers zu überprüfen und zu signieren. Wenn ein Zertifikat generiert wird, werden ein öffentlicher Schlüssel und ein privater Schlüssel erstellt. Nur der öffentliche Schlüssel wird freigegeben und signiert. Wie der Name schon sagt, wird der öffentliche Schlüssel jeder öffentlichen Anforderung zur Verfügung gestellt. Der öffentliche Schlüssel wird von Clients, Servern und anderen anfordernden Personen verwendet, die Informationen sicher austauschen und die Identität eines Computers überprüfen müssen. Der private Schlüssel wird gesichert und nur von dem Computer verwendet, der das Schlüsselpaar zum Entschlüsseln von Nachrichten, die mit seinem öffentlichen Schlüssel verschlüsselt wurden, erstellt hat. Der private Schlüssel kann für andere Zwecke verwendet werden. Für Reverse-Proxy-Zwecke ist die Datenverschlüsselung die hauptsächliche Verwendung. In zweiter Linie ist die Zertifikatauthentifizierung auf der Zertifikatschlüssel Ebene eine andere Verwendung und ist nur auf die Überprüfung eingeschränkt, die ein Anforderer über den öffentlichen Schlüssel des Computers verfügt, oder dass der Computer, für den Sie über einen öffentlichen Schlüssel verfügen, tatsächlich der Computer ist, den er vorgibt.



</div>

<div>


> [!TIP]
> Wenn Sie Ihre Edge-Server Zertifikate und ihre Reverse-Proxy Zertifikate gleichzeitig planen, sollten Sie feststellen, dass die beiden Zertifikatanforderungen sehr ähnlich sind. Wenn Sie Ihr Edge-Server-Zertifikat konfigurieren und anfordern, kombinieren Sie den Edgeserver und die alternativen Namen des Reverse Proxy-Subjekts. Sie können dasselbe Zertifikat für Ihren Reverseproxy verwenden, wenn Sie das Zertifikat und den privaten Schlüssel exportieren und die exportierte Datei in den Reverse-Proxy kopieren und dann das Zertifikat/Schlüsselpaar importieren und in den anstehenden Verfahren nach Bedarf zuweisen. Lesen Sie die Zertifikatanforderungen für den Edge-&nbsp;Server-<A href="lync-server-2013-plan-for-edge-server-certificates.md">Plan für Edge-Server-Zertifikate in lync Server 2013</A> und die <A href="lync-server-2013-certificate-summary-reverse-proxy.md">Zusammenfassung des Reverse-Proxy Zertifikats – Reverse Proxy in lync Server 2013</A>. Stellen Sie sicher, dass Sie das Zertifikat mit einem exportierbaren privaten Schlüssel erstellen. Das Erstellen des Zertifikats und der Zertifikatanforderung mit einem exportierbaren privaten Schlüssel ist für Pool-Edgeserver erforderlich, daher ist dies eine übliche Vorgehensweise, und der Zertifikat-Assistent im lync Server-Bereitstellungs-Assistenten für den Edgeserver ermöglicht es Ihnen, das exportierbare Kennzeichen <STRONG>privater Schlüssel machen</STRONG> zu definieren. Nachdem Sie die Zertifikatanforderung von der öffentlichen Zertifizierungsstelle zurück erhalten haben, werden Sie das Zertifikat und den privaten Schlüssel exportieren. Informationen zum Erstellen und Exportieren Ihres Zertifikats mit einem privaten Schlüssel finden Sie im Abschnitt "So exportieren Sie das Zertifikat mit dem privaten Schlüssel für Edgeserver in einem Pool" im Thema <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Einrichten von Zertifikaten für die externe Edge-Schnittstelle für lync Server 2013</A> . Die Erweiterung des Zertifikats sollte vom Typ <STRONG>PFX</STRONG>sein.



</div>

Führen Sie die folgenden Schritte aus, um eine Zertifikatsignaturanforderung auf dem Computer zu generieren, auf dem das Zertifikat und der private Schlüssel zugewiesen werden:

**Erstellen einer Zertifikatsignaturanforderung**

1.  Öffnen Sie die Microsoft Management Console (MMC), fügen Sie das Zertifikat-Snap-in hinzu, wählen Sie **Computer**aus, und erweitern Sie dann **Personal**. Ausführliche Informationen zum Erstellen einer Certificates-Konsole in der Microsoft Management Console (MMC) finden Sie [http://go.microsoft.com/fwlink/?LinkId=282616](http://go.microsoft.com/fwlink/?linkid=282616)unter.

2.  Klicken Sie mit der rechten Maustaste auf **Zertifikate**, klicken Sie auf **alle Aufgaben**, klicken Sie auf **Erweiterte Vorgänge**, klicken Sie auf **Benutzerdefinierte Anforderung erstellen**.

3.  Klicken Sie auf der Seite **Zertifikatregistrierung** auf **weiter**.

4.  Wählen Sie auf der Seite **Zertifikatregistrierungsrichtlinie auswählen** unter **Benutzerdefinierte Anforderung**die Option **ohne Registrierungsrichtlinie fortfahren**aus. Klicken Sie auf **Weiter**.

5.  Klicken Sie auf der Seite **Benutzerdefinierte Anforderung** für **Vorlage** auf **Legacy Schlüssel (ohne Vorlage)**. Wenn Ihr Zertifikatanbieter nichts anderes anwendet, Belasse die Option **Standarderweiterungen** deaktivieren und die Auswahl des **Anforderungs Formats** in ** \#PKCS 10**. Klicken Sie auf **Weiter**.

6.  Klicken Sie auf der Seite **Zertifikatinformationen** auf **Details**, und klicken Sie dann auf **Eigenschaften**.

7.  Geben Sie auf der Seite " **Zertifikateigenschaften** " auf der Registerkarte **Allgemein** im Feld **Anzeigename** einen Namen für dieses Zertifikat ein. Geben Sie optional im Feld **Beschreibung** eine Beschreibung ein. Der Anzeige Name und die Beschreibung werden in der Regel vom Administrator verwendet, um zu ermitteln, was der Zertifikatszweck ist, beispielsweise den **Reverse Proxy-Listener für lync Server**.

8.  Wählen Sie die Registerkarte **Betreff** aus. Wählen Sie unter **Antragstellername** für den **Typ**den Eintrag **allgemeiner Name** für den Typ des Antragstellernamens aus. Geben Sie für den **Wert**den Namen des Antragstellers ein, den Sie für den Reverse-Proxy verwenden möchten, und klicken Sie dann auf **Hinzufügen**. In dem Beispiel, das in der Tabelle in diesem Thema bereitgestellt wird, lautet der Name des Antragstellers Webext.contoso.com und wird in das Feld Wert für den Namen des Antragstellers eingegeben.

9.  Wählen Sie auf der Registerkarte **Betreff** unter **alternativer Name**in der Dropdownliste für **Typ**die Option **DNS** aus. Geben Sie für jeden definierten Betreff-alternativen Namen, den Sie für das Zertifikat benötigen, den vollqualifizierten Domänennamen ein, und klicken Sie dann auf **Hinzufügen**. In der Tabelle gibt es beispielsweise drei alternative Namen für Subjekte, Meet.contoso.com, dialin.contoso.com und lyncdiscover.contoso.com. Geben Sie im Feld **Wert** Meet.contoso.com ein, und klicken Sie auf **Hinzufügen**. Wiederholen Sie diesen Vorgang für jeden alternativen Betreff, den Sie definieren müssen.

10. Klicken Sie auf der Seite **Zertifikateigenschaften** auf die Registerkarte **Erweiterungen** . Auf dieser Seite definieren Sie die kryptografischen Schlüssel Zwecke in der **Schlüsselverwendung** und die erweiterte Schlüsselverwendung in der **erweiterten Schlüsselverwendung (Anwendungsrichtlinien)**.

11. Klicken Sie auf den Pfeil für die **Schlüsselverwendung** , um die **verfügbaren Optionen**anzuzeigen. Klicken Sie unter Verfügbare Optionen auf **digitale Signatur**, und klicken Sie dann auf **Hinzufügen**. Klicken Sie auf **Schlüssel Verschlüsselung**, und klicken Sie dann auf **Hinzufügen**. Aktivieren Sie das Kontrollkästchen, wenn das Kontrollkästchen für die **kritische Verwendung von Schlüsseln verwenden** deaktiviert ist.

12. Klicken Sie auf den Pfeil **Erweiterte Schlüsselverwendung (Anwendungsrichtlinien)** , um die **verfügbaren Optionen**anzuzeigen. Klicken Sie unter Verfügbare Optionen auf **Server Authentifizierung**und dann auf **Hinzufügen**. Klicken Sie auf **Client Authentifizierung**und dann auf **Hinzufügen**. Wenn das Kontrollkästchen für **die kritische Verwendung der erweiterten Schlüsselverwendung** aktiviert ist, deaktivieren Sie das Kontrollkästchen. Im Gegensatz zum Kontrollkästchen "Schlüsselverwendung" (das überprüft werden muss) müssen Sie sicherstellen, dass das Kontrollkästchen Erweiterte Schlüsselverwendung nicht aktiviert ist.

13. Klicken Sie auf der Seite **Zertifikateigenschaften** auf die Registerkarte **privater Schlüssel** . Klicken Sie auf den Pfeil mit den **Schlüsseloptionen** . Wählen Sie für **Schlüsselgröße**in der Dropdownliste **2048** aus. Wenn Sie dieses Schlüsselpaar und CSR auf einem anderen Computer als dem umgekehrten Proxy generieren, für den dieses Zertifikat vorgesehen ist, wählen Sie exportierbarer **privater Schlüssel erstellen**aus.
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="Sicherheits" alt="security" />Sicherheitshinweis:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Wenn Sie in einer Farm mehr als einen Reverse Proxy haben, werden Sie in der Regel darauf hingewiesen, <strong>dass</strong> Sie das Zertifikat und den privaten Schlüssel auf jeden Computer in der Farm kopieren. Wenn Sie einen exportierbaren privaten Schlüssel zulassen, müssen Sie mit dem Zertifikat und dem Computer, auf dem er erstellt wird, besonders vorsichtig vorgehen. Wenn der private Schlüssel beeinträchtigt wird, wird das Zertifikat unbrauchbar, und der Computer oder Computer können dem externen Zugriff und anderen Sicherheitsrisiken ausgesetzt werden.</td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. Klicken Sie auf der Registerkarte **privater Schlüssel** auf den Pfeil des **Tasten Typs** . Wählen Sie die Option **Exchange** aus.

15. Klicken Sie auf **OK** , um die von Ihnen festgelegten **Zertifikateigenschaften** zu speichern.

16. Klicken Sie auf der Seite **Zertifikatregistrierung** auf **weiter**.

17. Auf der Seite **wo möchten Sie die Offlineanforderung speichern?** werden Sie aufgefordert, einen **Dateinamen** und ein **Datei Format** zum Speichern der Zertifikatsignaturanforderung einzugeben.

18. Geben Sie im Feld Dateiname den Pfad und den Datei **Namen** für die Anforderung ein, oder klicken Sie auf **Durchsuchen** , um einen Speicherort für die Datei auszuwählen, und geben Sie den Dateinamen für die Anforderung ein.

19. Klicken Sie im Feld **Dateiformat**entweder auf **Basis 64** oder **Binär**. Wählen Sie **Basis 64** aus, es sei denn, Sie werden vom Hersteller anderweitig für Ihre Zertifikate angewiesen.

20. Suchen Sie die Anforderungsdatei, die Sie im vorherigen Schritt gespeichert haben. An Ihre öffentliche Zertifizierungsstelle übermitteln.
    
    <div>
    

    > [!IMPORTANT]
    > Microsoft hat öffentliche Zertifizierungsstellen identifiziert, die den Anforderungen für Unified Communications-Zwecke entsprechen. Eine Liste wird im folgenden Knowledge Base-Artikel verwaltet. <A href="http://go.microsoft.com/fwlink/?linkid=282625">http://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

