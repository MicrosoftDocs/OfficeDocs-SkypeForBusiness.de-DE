---
title: Anfordern und Konfigurieren eines Zertifikats für den Reverse-http-Proxy
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
ms.openlocfilehash: 7651e3da61e5ca197d36ca59ad8216af4c0188af
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511982"
---
# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a>Anfordern und Konfigurieren eines Zertifikats für den Reverse-http-Proxy in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-14_

Sie müssen das Zertifikat der Stammzertifizierungsstelle auf dem Server mit Microsoft Forefront Threat Management Gateway 2010 oder IIS arr für die Zertifizierungsstelleninfrastruktur installieren, die die Serverzertifikate für die internen Server mit Microsoft lync Server 2013 ausgestellt hat.

Sie müssen außerdem ein öffentliches Webserverzertifikat auf Ihrem Reverseproxyserver installieren. Die Liste der alternativen Antragstellernamen dieses Zertifikats sollte die veröffentlichten externen FQDNs für jeden Pool enthalten, in dem Benutzer verwaltet werden, die für den Remotezugriff aktiviert wurden. Außerdem muss das Zertifikat die externen FQDNs aller Directors oder Directorpools enthalten, die innerhalb dieser Edgeinfrastruktur verwendet werden. In den alternativen Antragstellernamen müssen außerdem die einfachen URLs für Besprechungen und Einwahl enthalten sein sowie – wenn Sie mobile Anwendungen bereitstellen und die Verwendung der AutoErmittlung planen – die externe AutoErmittlungsdienst-URL, wie im Folgenden gezeigt.


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
<td><p>Antragstellername</p></td>
<td><p>Pool-FQDN</p></td>
<td><p>webext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Alternativer Antragstellername</p></td>
<td><p>Pool-FQDN</p></td>
<td><p>webext.contoso.com</p>



> [!IMPORTANT]
> Der Antragstellername muss ebenfalls in den alternativen Antragstellernamen vorhanden sein.

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
> Alle einfachen URLs für Besprechungen müssen in den alternativen Antragstellernamen enthalten sein. Jede SIP-Domäne muss über mindestens eine aktive einfache URL für Besprechungen verfügen.

</td>
<td><p>meet.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>Alternativer Antragstellername</p></td>
<td><p>Einfache URLs vom Typ "Dialin"</p></td>
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
> Wenn Sie auch Exchange Server verwenden, müssen Sie auch Reverse-Proxy Regeln für die Exchange-Auto Ermittlungs-und Webdienste-URLs konfigurieren.

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> Wenn Ihre interne Bereitstellung mehr als einen Standard Edition-Server oder Front-End-Pool umfasst, müssen Sie Webveröffentlichungsregeln für jeden externen FQDN der Webfarm konfigurieren. Außerdem benötigen Sie entweder ein Zertifikat und einen Weblistener für jeden Eintrag, oder Sie müssen ein Zertifikat anfordern, dessen Liste alternativer Antragstellernamen die Namen enthält, die von allen Pools verwendet werden. Diese müssen einem Weblistener zugewiesen und in mehreren Webveröffentlichungsregeln gemeinsam verwendet werden.



</div>

<div>

## <a name="create-a-certificate-request"></a>Erstellen einer Zertifikatanforderung

Sie erstellen eine Zertifikatanforderung auf dem Reverse-Proxy. Sie erstellen eine Anforderung auf einem anderen Computer, aber Sie müssen das signierte Zertifikat mit dem privaten Schlüssel exportieren und auf den Reverseproxy importieren, nachdem Sie es von der öffentlichen Zertifizierungsstelle erhalten haben.

<div>


> [!NOTE]
> Eine Zertifikatanforderung oder eine zertifikatsignieranforderung (CSR) ist eine Anforderung an eine vertrauenswürdige öffentliche Zertifizierungsstelle (Certification Authority, ca), um den öffentlichen Schlüssel des anfordernden Computers zu validieren und zu signieren. Wenn ein Zertifikat generiert wird, werden ein öffentlicher Schlüssel und ein privater Schlüssel erstellt. Nur der öffentliche Schlüssel ist freigegeben und signiert. Wie der Name schon sagt, wird der öffentliche Schlüssel allen öffentlichen Anforderungen zur Verfügung gestellt. Der öffentliche Schlüssel wird für Clients, Server und andere Requestors verwendet, die Informationen sicher austauschen und die Identität eines Computers überprüfen müssen. Der private Schlüssel wird geschützt aufbewahrt und nur von dem Computer verwendet, der das Schlüsselpaar zum Entschlüsseln von Nachrichten erstellt hat, die mit seinem öffentlichen Schlüssel verschlüsselt wurden. Der private Schlüssel kann für andere Zwecke verwendet werden. Für Reverse-Proxy-Zwecke ist die Datenverschlüsselung die primäre Verwendung. Sekundär ist die Zertifikatauthentifizierung auf der Zertifikatschlüssel Ebene eine weitere Verwendung und beschränkt sich nur auf die Überprüfung, dass ein Anforderer über den öffentlichen Schlüssel des Computers verfügt, oder dass es sich bei dem Computer, für den Sie einen öffentlichen Schlüssel haben, um den Computer handelt, auf den er sich beruft.



</div>

<div>


> [!TIP]
> Wenn Sie Ihre Edgeserver Zertifikate und ihre Reverse-Proxy Zertifikate gleichzeitig planen, sollten Sie feststellen, dass es eine große Ähnlichkeit zwischen den beiden Zertifikatanforderungen gibt. Wenn Sie Ihr Edgeserver Zertifikat konfigurieren und anfordern, kombinieren Sie die Edgeserver und die alternativen Alternative Namen für den Reverseproxy. Sie können das gleiche Zertifikat für den Reverseproxy verwenden, wenn Sie das Zertifikat und den privaten Schlüssel exportieren und die exportierte Datei in den Reverseproxy kopieren und dann das Zertifikat/Schlüsselpaar importieren und nach Bedarf in den anstehenden Verfahren zuweisen. Lesen Sie die Zertifikatanforderungen für den Edgeserver &nbsp; <A href="lync-server-2013-plan-for-edge-server-certificates.md">Plan für Edgeserver Zertifikate in lync Server 2013</A> und die Zusammenfassung des Reverse Proxy <A href="lync-server-2013-certificate-summary-reverse-proxy.md">Zertifikats-Reverseproxy in lync Server 2013</A>. Stellen Sie sicher, dass Sie das Zertifikat mit einem exportierbaren privaten Schlüssel erstellen. Das Erstellen des Zertifikats und der Zertifikatanforderung mit einem exportierbaren privaten Schlüssel ist für gepoolte Edgeserver erforderlich, daher ist dies eine normale Vorgehensweise, und der Zertifikat-Assistent im lync Server-Bereitstellungs-Assistenten für die Edgeserver ermöglicht Ihnen das Festlegen des exportierbaren Kennzeichens <STRONG>privater Schlüssel</STRONG> . Nachdem Sie die Zertifikatanforderung von der öffentlichen Zertifizierungsstelle zurück erhalten haben, werden Sie das Zertifikat und den privaten Schlüssel exportieren. Weitere Informationen zum Erstellen und Exportieren Ihres Zertifikats mit einem privaten Schlüssel finden Sie im Abschnitt "So exportieren Sie das Zertifikat mit dem privaten Schlüssel für Edgeserver in einem Pool" im Thema <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Einrichten von Zertifikaten für die externe Edge-Schnittstelle für lync Server 2013</A> . Die Erweiterung des Zertifikats sollte vom Typ <STRONG>. pfx</STRONG>sein.



</div>

Führen Sie die folgenden Schritte aus, um eine Zertifikatsignaturanforderung auf dem Computer zu generieren, auf dem das Zertifikat und der private Schlüssel zugewiesen werden:

**Erstellen einer Zertifikatsignaturanforderung**

1.  Öffnen Sie die Microsoft Management Console (MMC), fügen Sie das Zertifikat-Snap-in hinzu, wählen Sie **Computer**aus, und erweitern Sie dann **Personal**. Ausführliche Informationen zum Erstellen einer Zertifikatkonsole in der Microsoft Management Console (MMC) finden Sie unter [https://go.microsoft.com/fwlink/?LinkId=282616](https://go.microsoft.com/fwlink/?linkid=282616) .

2.  Klicken Sie mit der rechten Maustaste auf **Zertifikate**, klicken Sie auf **alle Aufgaben**, klicken Sie auf **Erweiterte Vorgänge**und dann auf **Benutzerdefinierte Anforderung erstellen**.

3.  Klicken Sie auf der Seite **Zertifikatregistrierung** auf **weiter**.

4.  Wählen Sie auf der Seite **Zertifikatregistrierungsrichtlinie auswählen** unter **Benutzerdefinierte Anforderung**die Option **ohne Registrierungsrichtlinie fortfahren**aus. Klicken Sie auf **Weiter**.

5.  Klicken Sie auf der Seite **Benutzerdefinierte Anforderung** für **Vorlage** auswählen **(kein Vorlage) Legacy Schlüssel**. Wenn nicht anders von Ihrem Zertifikatanbieter verwiesen wird, lassen Sie die Option **Standarderweiterungen** deaktivieren und die Auswahl des **Anforderungs Formats** auf **PKCS \# 10**unterdrücken. Klicken Sie auf **Weiter**.

6.  Klicken Sie auf der Seite **Zertifikatinformationen** auf **Details**und dann auf **Eigenschaften**.

7.  Geben Sie auf der Seite **Zertifikateigenschaften** auf der Registerkarte **Allgemein** im Feld **Anzeigename** einen Namen für dieses Zertifikat ein. Geben Sie optional eine Beschreibung in das Feld **Beschreibung** ein. Der Anzeige Name und die Beschreibung werden normalerweise vom Administrator verwendet, um zu ermitteln, was das Zertifikatzweck ist, beispielsweise **für den Reverse Proxy Listener für lync Server**.

8.  Wählen Sie die Registerkarte **Betreff** aus. Wählen Sie unter **Antragstellername** für den **Typ**die Option **allgemeiner Name** für den Typ des Antragstellernamens aus. Geben Sie für den **Wert**den Antragstellernamen ein, den Sie für den Reverseproxy verwenden werden, und klicken Sie dann auf **Hinzufügen**. In dem in der Tabelle in diesem Thema angegebenen Beispiel lautet der Antragstellername Webext.contoso.com und würde in das Feld Wert für den Antragstellernamen eingegeben werden.

9.  Wählen Sie auf der Registerkarte **Betreff** unter **alternativer Name** **DNS** aus der Dropdownliste für **Type**aus. Geben Sie für jeden definierten alternativen Antragstellernamen, den Sie für das Zertifikat benötigen, den vollqualifizierten Domänennamen ein, und klicken Sie dann auf **Hinzufügen**. In der Tabelle gibt es beispielsweise drei alternative Antragstellernamen, Meet.contoso.com, dialin.contoso.com und lyncdiscover.contoso.com. Geben Sie Meet.contoso.com in das Feld **Wert** ein, und klicken Sie dann auf **Hinzufügen**. Wiederholen Sie diese Schritte für alle alternativen Antragstellernamen, die Sie definieren müssen.

10. Klicken Sie auf der Seite **Zertifikateigenschaften** auf die Registerkarte **Erweiterungen** . Auf dieser Seite definieren Sie die kryptografischen Schlüssel Zwecke in der **Schlüsselverwendung** und die erweiterte Schlüsselverwendung in der **erweiterten Schlüsselverwendung (Anwendungsrichtlinien)**.

11. Klicken Sie auf den Pfeil **Schlüsselverwendung** , um die **verfügbaren Optionen**anzuzeigen. Klicken Sie unter Verfügbare Optionen auf **digitale Signatur**, und klicken Sie dann auf **Hinzufügen**. Klicken Sie auf **Schlüssel Verschlüsselung**, und klicken Sie dann auf **Hinzufügen**. Aktivieren Sie das Kontrollkästchen, wenn das Kontrollkästchen für wichtige **Verwendungen dieser Schlüssel verwenden** deaktiviert ist.

12. Klicken Sie auf den Pfeil **Erweiterte Schlüsselverwendung (Anwendungsrichtlinien)** , um die **verfügbaren Optionen**anzuzeigen. Klicken Sie unter Verfügbare Optionen auf **Server Authentifizierung**, und klicken Sie dann auf **Hinzufügen**. Klicken Sie auf **Client Authentifizierung**und dann auf **Hinzufügen**. Wenn das Kontrollkästchen für **die Option Erweiterte Schlüsselverwendungen kritisch** aktiviert ist, deaktivieren Sie das Kontrollkästchen. Im Gegensatz zum Kontrollkästchen für die Schlüsselverwendung (das überprüft werden muss) müssen Sie sicherstellen, dass das Kontrollkästchen Erweiterte Schlüsselverwendung nicht aktiviert ist.

13. Klicken Sie auf der Seite **Zertifikateigenschaften** auf die Registerkarte **privater Schlüssel** . Klicken Sie auf den Pfeil mit den **Schlüsseloptionen** . Wählen Sie für die **Schlüsselgröße** **2048** aus der Dropdownliste aus. Wenn Sie dieses Schlüsselpaar und CSR auf einem anderen Computer als dem Reverse-Proxy generieren, für den dieses Zertifikat vorgesehen ist, wählen Sie exportierbaren **privaten Schlüssel erstellen**aus.
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="Sicherheits" alt="security" />Sicherheitshinweis:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Das auswählen <strong>eines exportierbaren privaten Schlüssels</strong> wird in der Regel empfohlen, wenn Sie mehr als einen Reverseproxy in einer Farm haben, da Sie das Zertifikat und den privaten Schlüssel auf jeden Computer in der Farm kopieren. Wenn Sie einen exportierbaren privaten Schlüssel zulassen, müssen Sie mit dem Zertifikat und dem Computer, auf dem es generiert wurde, besonders vorsichtig vorgehen. Bei Gefährdung des privaten Schlüssels wird das Zertifikat als nutzlos dargestellt, und der Computer oder Computer kann dem externen Zugriff und anderen Sicherheitsrisiken möglicherweise ausgesetzt werden.</td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. Klicken Sie auf der Registerkarte **privater Schlüssel** auf den Pfeil des **Schlüsseltyps** . Wählen Sie die Option **Exchange** aus.

15. Klicken Sie auf **OK** , um die festgelegten **Zertifikateigenschaften** zu speichern.

16. Klicken Sie auf der Seite **Zertifikatregistrierung** auf **weiter**.

17. Auf der Seite **wo möchten Sie die Offlineanforderung speichern?** werden Sie aufgefordert, einen **Dateinamen** und ein **Datei Format** zum Speichern der Zertifikatsignaturanforderung einzugeben.

18. Geben Sie im Feld Dateiname einen Pfad und einen Datei **Namen** für die Anforderung ein, oder klicken Sie auf **Durchsuchen** , um einen Speicherort für die Datei auszuwählen, und geben Sie den Dateinamen für die Anforderung ein.

19. Klicken Sie für das **Dateiformat**entweder auf **Base 64** oder **Binary**. Wählen Sie **Basis 64** , es sei denn, Sie werden vom Anbieter anderweitig für Ihre Zertifikate instruiert.

20. Suchen Sie die Anforderungsdatei, die Sie im vorherigen Schritt gespeichert haben. Übermitteln Sie Sie an Ihre öffentliche Zertifizierungsstelle.
    
    <div>
    

    > [!IMPORTANT]
    > Microsoft hat öffentliche Zertifizierungsstellen identifiziert, die die Anforderungen für Unified Communications Zwecke erfüllen. Eine Liste wird im folgenden Knowledge Base-Artikel verwaltet. <A href="https://go.microsoft.com/fwlink/?linkid=282625">https://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

