---
title: 'Lync Server 2013: Verwenden von lync-Skype-Konnektivität als Endbenutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Lync-Skype connectivity as an end user
ms:assetid: ad22f731-118c-4349-8790-b1a72941cbdd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440175(v=OCS.15)
ms:contentKeyID: 57793365
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6971ef2d6fb08838a4fcf71f4fec8097a7f9e47
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-lync-skype-connectivity-in-lync-server-2013-as-an-end-user"></a>Verwenden von lync-Skype-Konnektivität in lync Server 2013 als Endbenutzer

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-12-27_

Mit lync-Skype-Konnektivität können Skype-Benutzer und lync-Benutzer sich gegenseitig als Kontakte hinzufügen, Chatnachrichten austauschen und Audio-und Videoanrufe tätigen. Wenn ein Skype-Benutzer einen lync-Benutzer hinzufügt, erstellt ein Skype-Benutzer einen Kontakt in Skype, der den SIP-Uniform Resource Identifier (Session Initiation Protocol) des lync-Benutzers enthält. Wenn ein lync-Benutzer einen Skype-Kontakt hinzufügt, erstellt der lync-Benutzer umgekehrt einen Kontakt in lync, der das Microsoft-Konto (MSA) des Skype-Benutzers und nicht den Skype-Benutzernamen enthalten soll.

**Was ist eine MSA?** Skype-Benutzer müssen sich mit einem Microsoft-Konto (früher als Windows Live ID bezeichnet) bei Skype anmelden, um mit lync-Kontakten zu kommunizieren.Ein Microsoft-Konto besteht aus der Kombination aus einer e-Mail-Adresse und einem Kennwort, die Sie auch für die Anmeldung bei Diensten wie Microsoft OneDrive Speichertechnologie, Windows Phone, Microsoft Xbox Live Online Game Service und Microsoft Outlook Messaging verwenden können. und Zusammenarbeitsclient (und zuvor Microsoft Hotmail-webbasierter e-Mail-Dienst oder Windows Live Messenger).Wenn Sie eine e-Mail-Adresse und ein Kennwort verwenden, um sich bei diesen oder anderen Diensten anzumelden, verfügen Sie bereits über ein Microsoft-Konto.Ausführliche Informationen zum Erstellen eines Microsoft-Kontos finden Sie auf [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061)der Microsoft-Konto-Anmeldeseite unter. Sie können Ihr vorhandenes Skype-Konto mit Ihrem Microsoft-Konto für einmaliges Anmelden in einer Vielzahl von Anwendungen und Diensten zusammenführen. Nachdem das Konto zusammengeführt wurde, kann ein Skype-Benutzer eine Kontakt Anfrage an lync-Benutzer senden.

<div>


> [!IMPORTANT]  
> Damit lync-und Skype-Benutzer vollständig miteinander kommunizieren können, müssen die folgenden Voraussetzungen erfüllt sein: 
> <UL>
> <LI>
> <P>Skype-Benutzer müssen bei Ihrem Skype-Client mit einem Microsoft-Konto (MSA) angemeldet sein.</P>
> <LI>
> <P>Lync-Benutzer müssen für die Verbindung mit öffentlichen Chat Diensten durch ihren lync-Administrator aktiviert sein.</P>
> <LI>
> <P>Wenn ein Skype-Benutzer einen lync-Kontakt hinzufügt, vergewissern Sie sich, dass das Wort lync unter dem Namen des Kontakts angezeigt wird. Dies deutet darauf hin, dass ein lync-URI gefunden wurde.</P>
> <LI>
> <P>Wenn ein Skype-Benutzer einen lync-Kontakt hinzufügt und keine Suchergebnisse für diese lync-Domäne zurückgegeben werden, ist der PIC-bereit stellungsprozess möglicherweise nicht abgeschlossen, oder die lync-Domäne wurde noch nicht eingerichtet.</P>
> <LI>
> <P>Je nach den Datenschutzeinstellungen der lync-und Skype-Benutzer funktionieren Chat, Video und Anwesenheit möglicherweise erst, wenn die neuen Kontakte von jedem Benutzer akzeptiert werden.</P></LI></UL>



</div>

**So fügen Sie lync 2013 einen Skype-Kontakt hinzu**

1.  Klicken Sie in lync auf **Kontakt hinzufügen, fügen Sie einen Kontakt nicht in meine Organisation hinzu**.

2.  Wählen Sie in der Liste der verfügbaren Kontakt Anbieter **Skype**aus.

3.  Geben Sie in das Feld **Chat Adresse** das Microsoft-Konto (MSA) des Skype-Benutzers ein.

4.  Wählen Sie im Dropdownfeld **zur Kontaktgruppe hinzufügen** eine Kontaktgruppe aus, der der Benutzer hinzugefügt werden soll.

5.  Wählen Sie im Dropdownfeld **Datenschutz Beziehung festlegen** die entsprechende Kontakteinstellung aus, und klicken Sie dann auf **OK**.

6.  Der Benutzer wird nun als Kontakt in lync angezeigt. Wählen Sie den Benutzer aus, klicken Sie mit der rechten Maustaste auf den Benutzernamen, und klicken Sie auf Visiten **Karte** anzeigen, um die Benutzereigenschaften anzuzeigen. Sie können nun einen Audio-oder Videoanruf mit dem neu hinzugefügten Skype-Benutzer einrichten.

Weitere Informationen zur Unterstützung von Kontakten finden Sie unter [Hinzufügen eines Kontakts in lync](https://support.office.com/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a).

Wenn ein Microsoft-Konto eines Skype-Benutzers einen benutzerdefinierten Domänennamen wie <strong>Bob@contoso.com</strong> verwendet, kann ein lync-Benutzer dieses Microsoft-Konto auf zwei Arten zu lync hinzufügen:

1.  Verwenden Sie das Symbol " **Kontakt hinzufügen** " oder

2.  Verwenden Sie das Feld **jemanden suchen oder einen Raum oder ein Ziffernblatt wählen** .

In jeder Instanz muss der lync-Benutzer die e-Mail-Adresse des Skype-Benutzers im folgenden Format eingeben: <strong>Benutzer (Domänenname) @MSN. com</strong> .

<div>


> [!IMPORTANT]  
> Dieser Schritt ist für Microsoft-Konten, die die folgenden Domänennamen verwenden, nicht erforderlich: <STRONG>@Live. com, @hotmail. com oder @Outlook. com</STRONG>. Weitere Informationen zu unterstützten benutzerdefinierten Domänennamen finden Sie unter <A href="https://support.microsoft.com/kb/897567">Supported Public Chat Domains</A>.



</div>

**So fügen Sie lync einen Skype-Kontakt hinzu, wenn Sie einen benutzerdefinierten Domänennamen verwenden**

1.  Klicken Sie in lync auf **Kontakt hinzufügen, fügen Sie einen Kontakt nicht in meine Organisation hinzu**.

2.  Wählen Sie in der Liste der verfügbaren Kontakt Anbieter **Skype**aus.

3.  Geben Sie im Feld **Chat Adresse** das Microsoft-Konto (MSA) des Skype-Benutzers im Format <strong>Benutzer (Domänenname) @MSN. com</strong>ein. Für Benutzer Bob@contoso.com wäre der Eintrag also <strong>Bob (contoso. com) @MSN. com.<strong>

4.  Wählen Sie im Dropdown-Listenfeld **zu Kontaktgruppe hinzufügen** eine Kontaktgruppe aus, der der Benutzer hinzugefügt werden soll.

5.  Wählen Sie im Dropdown-Listenfeld **Datenschutz Beziehung festlegen** die entsprechende Kontakteinstellung aus, und klicken Sie dann auf **OK**.

6.  Ein lync-Benutzer kann auch den **Suchbegriff "jemand" oder einen Raum verwenden oder ein Nummern** Feld in lync wählen und eine Adresse hinzufügen, die dem folgenden <strong>Benutzer (Domänenname) @MSN. com</strong> ähnelt. Für das Bob@contoso.com Microsoft-Konto wäre der Eintrag also <strong>Bob (contoso. com) @MSN. com</strong> .

7.  Führen Sie die Schritte 4 und 5 weiter oben in diesem Verfahren aus, um den Kontakt einer Kontaktgruppe hinzuzufügen und die entsprechende Datenschutz Beziehung auszuwählen.

**So fügen Sie Skype einen lync-Kontakt hinzu**

1.  Melden Sie sich bei Skype an. Der Skype-Benutzer muss bei seinem Skype-Client mit einem Microsoft-Konto (MSA) angemeldet sein.

2.  Wählen Sie das Symbol Kontakte hinzufügen aus.

3.  Geben Sie den SIP-URI des lync-Benutzers ein. Beispiel: bob@contoso.com.

4.  Wenn Skype die Übereinstimmung in den Suchergebnissen findet, suchen Sie nach dem Wort **lync** unter dem Namen des lync-Benutzers. Dies deutet darauf hin, dass Skype erfolgreich den SIP-URI des lync-Clients gefunden hat. Klicken Sie auf den Namen.

5.  Klicken Sie in der oberen rechten Ecke des Fensters auf zu Kontakten hinzufügen.

6.  Der neue Kontakt wird nun Ihrer Kontaktliste hinzugefügt, aber anstelle des Statussymbols wird ein Fragezeichen angezeigt, bis Sie Ihre Anfrage annehmen. Wenn Ihr neuer Kontakt Ihre Anfrage annimmt, können Sie sehen, wann diese online sind, Chat Unterhaltungen initiieren und Audio-und Videoanrufe tätigen.
    
    <div>
    

    > [!IMPORTANT]  
    > Der lync Server Administrator muss die Richtlinieneinstellungen des lync-Benutzers so konfigurieren, dass eingehende Anforderungen zulässig sind. Wenn dies nicht der Fall ist, erhält der lync-Benutzer keine Kontaktanforderungen vom Skype-Benutzer. In Abhängigkeit von der Konfiguration der Richtlinieneinstellungen des lync-Benutzers wird die Anforderung zum Hinzufügen des Skype-Benutzers auf der <STRONG>neuen</STRONG> Registerkarte des lync-Clients angezeigt. Um mit der Kommunikation mit dem Skype-Benutzer zu beginnen, muss der lync-Benutzer den Skype-Benutzer entweder der Favoritenliste oder einer Kontaktliste hinzufügen. Das folgende Bild zeigt den Speicherort der <STRONG>neuen</STRONG> Registerkarte im lync-Client.

    
    </div>

Ein lync-Benutzer muss lync-Warnungen konfigurieren, um sicherzustellen, dass von einem Skype-Benutzer gesendete Anforderungen angezeigt werden und vom lync-Benutzer erkannt werden können. Um lync-Warnungen zu konfigurieren, führen Sie das folgende Verfahren aus.

**So konfigurieren Sie lync-Warnungen**

1.  Klicken Sie auf dem lync-Client auf das **options** Symbol.

2.  Wählen Sie **Warnungen**aus.

3.  Überprüfen Sie unter **Allgemeine Warnungen**, **Wenn mich jemand zu seiner Kontaktliste hinzufügt, auf Benachrichtigen**.

4.  Wählen Sie unter Kontakte, die **lync nicht verwenden** **die Option Einladungen zulassen, aber alle anderen Kommunikationen blockieren**aus.

5.  Klicken Sie auf **OK** , um das Fenster Optionen zu schließen.

</div>

<span> </span>

</div>

</div>

</div>

