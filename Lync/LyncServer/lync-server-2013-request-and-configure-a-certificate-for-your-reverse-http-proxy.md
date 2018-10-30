---
title: 'Lync Server 2013: Anfordern und Konfigurieren eines Zertifikats für den HTTP-Reverseproxy'
TOCTitle: Anfordern und Konfigurieren eines Zertifikats für den HTTP-Reverseproxy
ms:assetid: 4b70991e-5f10-40a3-b069-0b227c3a3a0a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg429704(v=OCS.15)
ms:contentKeyID: 49293927
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anfordern und Konfigurieren eines Zertifikats für den HTTP-Reverseproxy in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Sie müssen für die Zertifizierungsstelleninfrastruktur, mit der die Serverzertifikate der Server mit Microsoft Lync Server 2013 ausgestellt wurden, das Zertifikat der Stammzertifizierungsstelle auf dem Server installieren, auf dem Microsoft Forefront Threat Management Gateway 2010 oder IIS ARR ausgeführt wird.

Sie müssen außerdem ein öffentliches Webserverzertifikat auf Ihrem Reverseproxyserver installieren. Die Liste der alternativen Antragstellernamen dieses Zertifikats sollte die veröffentlichten externen FQDNs für jeden Pool enthalten, in dem Benutzer verwaltet werden, die für den Remotezugriff aktiviert wurden. Außerdem muss das Zertifikat die externen FQDNs aller Directors oder Directorpools enthalten, die innerhalb dieser Edgeinfrastruktur verwendet werden. In den alternativen Antragstellernamen müssen außerdem die einfachen URLs für Besprechungen und Einwahl enthalten sein sowie - wenn Sie mobile Anwendungen bereitstellen und die Verwendung der AutoErmittlung planen - die externe AutoErmittlungsdienst-URL, wie im Folgenden gezeigt.


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
<div>

> [!IMPORTANT]
> Der Antragstellername muss ebenfalls in den alternativen Antragstellernamen vorhanden sein.


</div></td>
</tr>
<tr class="odd">
<td><p>Alternativer Antragstellername</p></td>
<td><p>Optional Director Web Services (wenn Director bereitgestellt wird)</p></td>
<td><p>webdirext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Alternativer Antragstellername</p></td>
<td><p>Einfache URL für Besprechungen</p>
<div>

> [!NOTE]
> Alle einfachen URLs für Besprechungen müssen in den alternativen Antragstellernamen enthalten sein. Jede SIP-Domäne muss über mindestens eine aktive einfache URL für Besprechungen verfügen.


</div></td>
<td><p>meet.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>Alternativer Antragstellername</p></td>
<td><p>Einfache URLs vom Typ &quot;Dialin&quot;</p></td>
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
<div>

> [!NOTE]
> Wenn Sie auch mit Microsoft Exchange Server arbeiten, müssen Sie zusätzlich Reverseproxyregeln für die AutoErmittlung- und Webdienste-URLs von Exchange konfigurieren.


</div></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Wenn Ihre interne Bereitstellung mehr als einen Standard Edition-Server oder Front-End-Pool umfasst, müssen Sie Webveröffentlichungsregeln für jeden externen FQDN der Webfarm konfigurieren. Außerdem benötigen Sie entweder ein Zertifikat und einen Weblistener für jeden Eintrag, oder Sie müssen ein Zertifikat anfordern, dessen Liste alternativer Antragstellernamen die Namen enthält, die von allen Pools verwendet werden. Diese müssen einem Weblistener zugewiesen und in mehreren Webveröffentlichungsregeln gemeinsam verwendet werden.



## Erstellen einer Zertifikatanforderung

Eine Zertifikatanforderung erstellen Sie auf dem Reverseproxy. Sie erstellen eine Anforderung auf einem anderen Computer, müssen das signierte Zertifikat mit dem privaten Schlüssel aber exportieren und in den Reverseproxy importieren, sobald Sie es von der öffentlichen Zertifizierungsstelle erhalten haben.


> [!NOTE]
> Eine Zertifikatanforderung oder Zertifikatsignieranforderung (Certificate Signing Request, CSR) ist eine Anforderung, in der eine vertrauenswürdige öffentliche Zertifizierungsstelle gebeten wird, den öffentlichen Schlüssel des anfordernden Computers zu überprüfen und zu signieren. Wenn ein Zertifikat generiert wird, werden ein öffentlicher Schlüssel und ein privater Schlüssel erstellt. Nur der öffentliche Schlüssel wird freigegeben und signiert. Wie dem Namen zu entnehmen ist, wird der öffentliche Schlüssel für jede öffentliche Anforderung bereitgestellt. Der öffentliche Schlüssel ist für die Verwendung durch Clients, Server und sonstige anfordernde Elemente vorgesehen, die Informationen sicher austauschen und die Identität eines Computers überprüfen müssen. Der private Schlüssel wird sicher verwahrt und nur von dem Computer, der das Schlüsselpaar erstellt hat, dazu verwendet, Nachrichten zu entschlüsselm, die mit seinem öffentlichen Schlüssel verschlüsselt wurden. Der private Schlüssel kann für andere Zwecke verwendet werden. Für Reverseproxyzwecke ist Datenverschlüsselung die Hauptverwendung. Zweitrangig ist die Zertifikatauthentifizierung auf Zertifikatschlüsselebene eine weitere Verwendung. Diese ist aber auf die Überprüfung beschränkt, dass das anfordernde Element den öffentlichen Schlüssel des Computers hat oder dass der Computer, für den Sie einen öffentlichen Schlüssel haben, tatsächlich der Computer ist, der er vorgibt zu sein.




> [!TIP]
> Wenn Sie Ihre Edgeserver-Zertifikate und Reverseproxyzertifikate gleichzeitig planen, sollten Sie daran denken, dass es ein großes Maß an Übereinstimmung zwischen den beiden Zertifikatanforderungen gibt. Wenn Sie Ihr Edgeserver-Zertifikat konfigurieren und anfordern, können Sie die alternativen Edgeserver- und Reverseproxy-Antragstellennamen kombinieren. Sie können dasselbe Zertifikat für Ihren Reverseproxy verwenden, wenn Sie das Zertifikat und den privaten Schlüssel exportieren, die exportierte Datei auf den Reverseproxy kopieren, das Zertifikat/Schlüssel-Paar importieren und dieses dann in späteren Schrittfolgen nach Bedarf zuweisen. Informationen zu den Zertifikatanforderungen finden Sie hier: für den Edgeserver&nbsp; <A href="lync-server-2013-plan-for-edge-server-certificates.md">Planen von Edgeserver-Zertifikaten in Lync Server 2013</A> und für den Reverseproxy <A href="lync-server-2013-certificate-summary-reverse-proxy.md">Zertifikatzusammenfassung für Reverseproxy in Lync Server 2013</A>. Achten Sie darauf, dass Sie das Zertifikat mit einem exportierbaren privaten Schlüssel erstellen. Ein Erstellen des Zertikats und der Zertifikatanforderung mit einem exportierbaren Schlüssel ist für Edgeserver erforderlich, die in einem Pool zusammengefasst sind. Dies ist also gängige Praxis, und der Zertifikat-Assistent im Lync Server-Bereitstellungs-Assistent für den Edgeserver ermöglicht es Ihnen, die Option <STRONG>Privaten Schlüssel exportierbar machen</STRONG> festzulegen. Nachdem Sie die Zertikatanforderung von der öffentlichen Zertifizierungsstelle zurückerhalten haben, exportieren Sie das Zertifikat und den privaten Schlüssel. Ausführliche Informationen, wie ein Zertifikat mit einem privaten Schlüssel erstellt und exportiert werden kann, finden Sie im Abschnitt "So exportieren Sie das Zertifikat mit dem privaten Schlüssel für Edgeserver in einem Pool" im Thema <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Einrichten der Zertifikate für die externe Edgeschnittstelle für Lync Server 2013</A>. Die Zertifikatdatei muss die Erweiterung <STRONG>PFX</STRONG> haben.



Wenn Sie eine Zertifikatsignieranforderung auf dem Computer erstellen möchten, auf dem das Zertifikat und der private Schlüssel zugewiesen werden sollen, gehen Sie wie folgt vor:

**Erstellen einer Zertifikatsignieranforderung**

1.  Öffnen Sie die Microsoft Management Console (MMC), fügen Sie das Zertifikate-Snap-In hinzu, wählen Sie **Computer** aus, und erweitern Sie dann **Eigene Zertifikate** . Informationen, wie eine Zertifikatekonsole in der Microsoft Management Console (MMC) erstellt wird, finden Sie unter [http://go.microsoft.com/fwlink/?LinkId=282616](http://go.microsoft.com/fwlink/?linkid=282616).

2.  Klicken Sie mit der rechten Maustaste auf **Zertifikate** , zeigen Sie auf **Alle Aufgaben** , zeigen Sie auf **Erweiterte Vorgänge** , und klicken Sie auf **Benutzerdefinierte Anforderung erstellen** .

3.  Klicken Sie auf der Seite **Zertifikatregistrierung** auf **Weiter** .

4.  Wählen Sie auf der Seite **Zertifikatregistrierungsrichtlinie auswählen** unter **Benutzerdefinierte Anforderung** die Option **Den Vorgang ohne Registrierungsrichtlinie fortsetzen** aus. Klicken Sie auf **Weiter** .

5.  Wählen Sie auf der Seite **Benutzerdefinierte Anforderung** für **Vorlage** die Option **(Keine Vorlage) Legacyschlüssel** aus. Sofern Ihr Zertifikatanbieter Ihnen nichts anderes mitgeteilt hat, belassen Sie **Standarderweiterungen unterdrücken** deaktiviert, und übernehmen Sie für **Anforderungsformat** die Auswahl **PKCS \#10** . Klicken Sie auf **Weiter** .

6.  Klicken Sie auf der Seite **Zertifikatsinformationen** auf **Details** , und klicken Sie dann auf **Eigenschaften** .

7.  Geben Sie auf der Seite **Zertifikateigenschaften** auf der Registerkarte **Allgemein** in das Feld **Anzeigename** den Namen für dieses Zertifikat ein. Geben Sie optional eine Beschreibung in das Feld **Beschreibung** ein. Der Anzeigename und die Beschreibung werden von einem Administrator üblicherweise dazu genutzt, den Zweck des jeweiligen Zertifikats anzugeben, etwa **Reverseproxylistener für Lync Server**.

8.  Wählen Sie die Registerkarte **Antragsteller** aus. Wählen Sie unter **Antragstellername** für **Typ** die Option **Allgemeiner Name** aus. Geben Sie für **Wert** den Antragstellernamen ein, den Sie für den Reverseproxy verwenden möchten, und klicken Sie dann auf **Hinzufügen** . In dem Beispiel, das in der Tabelle in diesem Thema aufgeführt ist, lautet der Antragstellername "webext.contoso.com", und dieser Name müsste für "Antragstellername" in das Feld "Wert" eingegeben werden.

9.  Wählen Sie auf der Registerkarte **Antragsteller** unter **Alternativer Name** in der Dropdownliste **Typ** die Option **DNS** aus. Geben Sie für jeden alternativen Antragstellernamen, den Sie für das Zertifikat benötigen, den vollqualifizierten Domänennamen ein, und klicken Sie dann auf **Hinzufügen** . Die Tabelle weiter oben enthält beispielsweise drei alternative Antragstellernamen: "meet.contoso.com", "dialin.contoso.com" und "lyncdiscover.contoso.com". Geben Sie "meet.contoso.com" in das Feld **Wert** ein, und klicken Sie dann auf **Hinzufügen** . Wiederholen Sie diesen Schritt für jeden alternativen Antragstellernamen, den Sie definieren müssen.

10. Klicken Sie auf der Seite **Zertifikateigenschaften** auf die Registerkarte **Erweiterungen** . Auf dieser Registerkarte geben Sie in **Schlüsselverwendung** die Verwendungszwecke für den Kryptografieschlüssel und in **Erweiterte Schlüsselverwendung (Anwendungsrichtlinien)** die erweiterte Schlüsselverwendung an.

11. Klicken Sie auf den Pfeil von **Schlüsselverwendung** , damit die Liste **Verfügbare Optionen** angezeigt wird. Klicken Sie unter **Verfügbare Optionen** auf **Digitale Signatur** , und klicken Sie dann auf **Hinzufügen** . Klicken Sie auf **Schlüsselverschlüsselung** , und klicken Sie dann auf **Hinzufügen** . Ist das Kontrollkästchen für **Diese Schlüsselverwendungen sind entscheidend** nicht aktiviert, aktivieren Sie es.

12. Klicken Sie auf den Pfeil von **Erweiterte Schlüsselverwendung (Anwendungsrichtlinien)** , damit die Liste **Verfügbare Optionen** angezeigt wird. Klicken Sie unter **Verfügbare Optionen** auf **Serverauthentfizierung** , und klicken Sie dann auf **Hinzufügen** . Klicken Sie auf **Clientauthentifizierung** und dann auf **Hinzufügen** . Ist das Kontrollkästchen **Erweiterte Schlüsselverwendung ist entscheidend** aktiviert, deaktivieren Sie es. Im Gegensatz zu dem Kontrollkästchen für Schlüsselverwendung (das aktiviert sein muss) darf das Kontrollkästchen für die erweiterte Schlüsselverwendung nicht aktiviert sein.

13. Klicken Sie auf der Seite **Zertifikateigenschaften** auf die Registerkarte **Privater Schlüssel** . Klicken Sie auf den Pfeil von **Schlüsseloptionen** . Wählen Sie in der Dropdownliste **Schlüsselgröße** die Option **2048** aus. Wenn Sie dieses Schlüsselpaar und diese Zertifikatsignieranforderung nicht auf dem Reverseproxy, für den dieses Zertifikat vorgesehen ist, sondern auf einem anderen Computer erstellen, aktivieren Sie **Privaten Schlüssel exportierbar machen** .
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg399038.security(OCS.15).gif" title="security" alt="security" />Sicherheit Hinweis:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Das Aktivieren von <strong>Privaten Schlüssel exportierbar machen</strong> empfiehlt sich grundsätzlich, wenn Sie mehrere Reverseproxys in einer Farm haben, weil Sie das Zertifikat und den privaten Schlüssel auf jeden Computer in der Farm kopieren. Wenn Sie kein Exportieren eines privaten Schlüssels zulassen, müssen Sie dem Zertifikat und dem Computer, auf dem das Zertifikat generiert wurde, zusätzliche Aufmerksamkeit widmen. Erfolgt eine Beeinträchtigung des privaten Schlüssels, lässt er das Zertifikat unbrauchbar werden und ergibt sich die Gefahr, dass der oder die Computer externem Zugriff und anderen Sicherheitsrisiken ausgesetzt werden.</td>
    </tr>
    </tbody>
    </table>


14. Klicken Sie auf der Registerkarte **Privater Schlüssel** auf den Pfeil von **Schlüsseltyp** . Wählen Sie die Option **Exchange** aus.

15. Klicken Sie auf **OK** , damit die von Ihnen festgelegten **Zertifikateigenschaften** gespeichert werden.

16. Klicken Sie auf der Seite **Zertifikatregistrierung** auf **Weiter** .

17. Auf der Seite **Wohin möchten Sie die Offlineanforderung speichern?** werden Sie aufgefordert, **Dateiname** und **Dateiformat** für das Speichern der Zertifikatsignieranforderung einzugeben.

18. Geben Sie in das Feld **Dateiname** den Pfad und den Dateinamen für die Anforderung ein, oder klicken Sie auf **Durchsuchen** , um den Speicherort für die Datei auszuwählen, und geben Sie den Dateinamen für die Anforderung ein.

19. Klicken Sie für **Dateiformat** auf **Base 64** oder auf **Binär** . Wählen Sie **Base 64** aus, sofern der Anbieter für Ihre Zertifikate Ihnen keine andere Anweisung gegeben hat.

20. Suchen Sie nach der Anforderungsdatei, die Sie im vorherigen Schritt gespeichert haben. Übermitteln Sie die Datei an Ihre öffentliche Zertifizierungsstelle.
    

    > [!IMPORTANT]
    > Microsoft hat öffentliche Zertifizierungsstellen ermittelt, die den Anforderungen für Unified Communications-Zwecke entsprechen. Eine entsprechende Liste wird in dem folgenden Knowledge Base-Artikel gepflegt: <A href="http://go.microsoft.com/fwlink/?linkid=282625">http://go.microsoft.com/fwlink/?LinkId=282625</A>


