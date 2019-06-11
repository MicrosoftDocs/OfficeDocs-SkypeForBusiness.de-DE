---
title: 'Lync Server 2013: Verwenden von Lync-Skype-Konnektivität als Endbenutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Lync-Skype connectivity as an end user
ms:assetid: ad22f731-118c-4349-8790-b1a72941cbdd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440175(v=OCS.15)
ms:contentKeyID: 57793365
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d2bf4584f3332171942f941cc382d22bb6a8db7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-lync-skype-connectivity-in-lync-server-2013-as-an-end-user"></a>Verwenden von Lync-Skype-Konnektivität als Endbenutzer in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-12-27_

Mit lync – Skype-Konnektivität können Skype-Benutzer und lync-Nutzer sich gegenseitig als Kontakte hinzufügen, Sofortnachrichten austauschen sowie Audio-und Videoanrufe tätigen. Wenn ein Skype-Nutzer einen lync-Nutzer hinzufügt, wird ein Skype-Nutzer einen Kontakt in Skype erstellen, der den SIP-Uniform Resource Identifier (Session Initiation Protocol) des lync-Benutzers enthält. Wenn ein lync-Benutzer einen Skype-Kontakt hinzufügt, erstellt der lync-Benutzer umgekehrt einen Kontakt in lync, der das Microsoft-Konto (MSA) des Skype-Benutzers und nicht den Skype-Nutzernamen enthält.

**Was ist ein MSA?** Skype-Nutzer müssen sich mit einem Microsoft-Konto (vormals als Windows Live ID bezeichnet) bei Skype anmelden, um mit lync-Kontakten zu kommunizieren.Ein Microsoft-Konto besteht aus einer Kombination aus einer e-Mail-Adresse und einem Kennwort, mit der Sie sich auch bei Diensten wie Microsoft OneDrive-Speichertechnologie, Windows Phone, Microsoft Xbox Live Online-Spielservice und Microsoft Outlook-Messaging anmelden können. und Zusammenarbeitsclient (und zuvor Microsoft Hotmail-webbasierter e-Mail-Dienst oder Windows Live Messenger).Wenn Sie eine e-Mail-Adresse und ein Kennwort für die Anmeldung bei diesen oder anderen Diensten verwenden, verfügen Sie bereits über ein Microsoft-Konto.Details zum Erstellen eines Microsoft-Kontos finden Sie auf [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061)der Anmeldeseite des Microsoft-Kontos unter. Sie können Ihr vorhandenes Skype-Konto mit Ihrem Microsoft-Konto für einmaliges Anmelden in einer Vielzahl von Anwendungen und Diensten zusammenführen. Nachdem das Konto zusammengeführt wurde, kann ein Skype-Nutzer eine Kontakt Anfrage an lync-Nutzer senden.

<div>


> [!IMPORTANT]  
> Damit lync-und Skype-Benutzer vollständig miteinander kommunizieren können, müssen die folgenden Voraussetzungen erfüllt sein: 
> <UL>
> <LI>
> <P>Skype-Nutzer müssen bei Ihrem Skype-Client mit einem Microsoft-Konto (MSA) angemeldet sein.</P>
> <LI>
> <P>Lync-Benutzer müssen für die Verbindung mit öffentlichen Chat Diensten durch ihren lync-Administrator aktiviert sein.</P>
> <LI>
> <P>Wenn ein Skype-Nutzer einen lync-Kontakt hinzufügt, stellen Sie sicher, dass das Wort lync unter dem Namen des Kontakts angezeigt wird. Dies zeigt an, dass ein lync-URI gefunden wurde.</P>
> <LI>
> <P>Wenn ein Skype-Benutzer einen lync-Kontakt hinzufügt und für diese lync-Domäne keine Suchergebnisse zurückgegeben werden, ist der PIC-Bereitstellungsprozess möglicherweise nicht abgeschlossen, oder die lync-Domäne wurde noch nicht eingerichtet.</P>
> <LI>
> <P>Je nach den Privatsphäre-Einstellungen der lync-und Skype-Nutzer funktionieren Chat, Video und Anwesenheitsinformationen möglicherweise erst, wenn die neuen Kontakte von jedem Benutzer akzeptiert werden.</P></LI></UL>



</div>

**So fügen Sie einen Skype-Kontakt zu lync 2013 hinzu**

1.  Klicken Sie in lync auf **Kontakt hinzufügen, einen Kontakt hinzufügen, der sich nicht in meiner Organisation**befindet.

2.  Wählen Sie in der Liste der verfügbaren Kontakt Anbieter **Skype**aus.

3.  Geben Sie im Feld **Chat Adresse** das Microsoft-Konto (MSA) des Skype-Benutzers ein.

4.  Wählen Sie im Dropdownfeld **zur Kontaktgruppe hinzufügen** eine Kontaktgruppe aus, der Sie den Benutzer hinzufügen möchten.

5.  Wählen Sie im Dropdownfeld **private Beziehung festlegen** die entsprechende Kontakteinstellung aus, und klicken Sie dann auf **OK**.

6.  Der Benutzer wird nun in lync als Kontakt angezeigt. Wählen Sie den Benutzer aus, klicken Sie mit der rechten Maustaste auf den Benutzernamen, und klicken Sie auf **Visitenkarte** anzeigen, um die Benutzereigenschaften anzuzeigen. Sie können jetzt mit dem neu hinzugefügten Skype-Nutzer einen Audio-oder Videoanruf einrichten.

Weitere Informationen zur Unterstützung von Kontakten finden Sie unter [Hinzufügen eines Kontakts in lync](https://support.office.com/en-us/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a).

Wenn das Microsoft-Konto eines Skype-Benutzers einen benutzerdefinierten Domänennamen wie <strong>Bob@contoso.com</strong> verwendet, kann ein lync-Benutzer dieses Microsoft-Konto auf zwei Arten zu lync hinzufügen:

1.  Verwenden Sie das Symbol " **Kontakt hinzufügen** " oder

2.  Verwenden Sie das Feld **jemanden suchen oder ein Zimmer oder ein Nummernfeld wählen** .

In jedem Fall muss der lync-Benutzer die e-Mail-Adresse des Skype-Benutzers im folgenden Format eingeben: <strong>Benutzer (Domänenname) @MSN. com</strong> .

<div>


> [!IMPORTANT]  
> Dieser Schritt ist für Microsoft-Konten, die die folgenden Domänennamen verwenden, nicht erforderlich: <STRONG>@Live. com, @hotmail. com oder @Outlook. com</STRONG>. Weitere Informationen zu unterstützten benutzerdefinierten Domänennamen finden Sie unter <A href="https://support.microsoft.com/kb/897567">Unterstützte öffentliche Chat-Domänen</A>.



</div>

**So fügen Sie einen Skype-Kontakt zu lync hinzu, wenn Sie einen benutzerdefinierten Domänennamen verwenden**

1.  Klicken Sie in lync auf **Kontakt hinzufügen, einen Kontakt hinzufügen, der sich nicht in meiner Organisation**befindet.

2.  Wählen Sie in der Liste der verfügbaren Kontakt Anbieter **Skype**aus.

3.  Geben Sie im Feld **Chat Adresse** das Microsoft-Konto (MSA) des Skype-Benutzers im Format <strong>User (Domain Name) @MSN. com</strong>ein. Für Benutzer Bob@contoso.com wäre der Eintrag also <strong>Bob (contoso. com) @MSN. com.<strong>

4.  Wählen Sie im Dropdown-Listenfeld **zu Kontaktgruppe hinzufügen** eine Kontaktgruppe aus, der Sie den Benutzer hinzufügen möchten.

5.  Wählen Sie im Dropdown-Listenfeld **private Beziehung festlegen** die entsprechende Kontakteinstellung aus, und klicken Sie dann auf **OK**.

6.  Ein lync-Benutzer kann auch das Feld **jemanden suchen oder einen Chatroom verwenden oder ein Nummern** Feld in lync wählen und eine Adresse hinzufügen, die dem folgenden <strong>Benutzer ähnelt (Domänenname) @MSN. com</strong> . Für das Bob@contoso.com-Microsoft-Konto wäre der Eintrag also <strong>Bob (contoso. com) @MSN. com</strong> .

7.  Führen Sie die Schritte 4 und 5 weiter oben in diesem Verfahren aus, um den Kontakt einer Kontaktgruppe hinzuzufügen und die entsprechende Datenschutz Beziehung auszuwählen.

**So fügen Sie einen lync-Kontakt zu Skype hinzu**

1.  Bei Skype anmelden. Der Skype-Nutzer muss bei seinem Skype-Client mit einem Microsoft-Konto (MSA) angemeldet sein.

2.  Wählen Sie das Symbol "Kontakte hinzufügen" aus.

3.  Geben Sie den SIP-URI des lync-Benutzers ein. Beispiel: Bob@contoso.com.

4.  Wenn Skype die Übereinstimmung in den Suchergebnissen findet, suchen Sie nach dem Wort **lync** unter dem Namen des lync-Benutzers. Dies zeigt an, dass Skype den SIP-URI des lync-Clients erfolgreich gefunden hat. Klicken Sie auf den Namen.

5.  Klicken Sie in der oberen rechten Ecke des Fensters auf zu Kontakten hinzufügen.

6.  Der neue Kontakt wird nun Ihrer Kontaktliste hinzugefügt, aber anstelle des Statussymbols wird ein Fragezeichen angezeigt, bis Sie Ihre Anfrage angenommen haben. Wenn Ihr neuer Kontakt Ihre Anfrage akzeptiert, können Sie sehen, wann Sie online sind, Chat Unterhaltungen initiieren und Audio-und Videoanrufe tätigen.
    
    <div>
    

    > [!IMPORTANT]  
    > Der lync Server-Administrator muss die Richtlinieneinstellungen des lync-Benutzers so konfigurieren, dass eingehende Anforderungen zulässig sind. Wenn dies nicht der Fall ist, erhält der lync-Nutzer keine Kontaktanfragen vom Skype-Nutzer. Je nach Konfiguration der Richtlinieneinstellungen des lync-Benutzers wird die Anforderung zum Hinzufügen des Skype-Benutzers auf der <STRONG>neuen</STRONG> Registerkarte des lync-Clients angezeigt. Um mit dem Skype-Nutzer kommunizieren zu können, muss der lync-Nutzer den Skype-Nutzer entweder der Favoritenliste oder einer Kontaktliste hinzufügen. Die folgende Abbildung zeigt die Position der <STRONG>neuen</STRONG> Registerkarte im lync-Client.

    
    </div>

Ein lync-Benutzer muss lync-Benachrichtigungen konfigurieren, um sicherzustellen, dass von einem Skype-Benutzer gesendete Anforderungen angezeigt werden und vom lync-Benutzer erkannt werden. Führen Sie die folgenden Schritte aus, um lync-Benachrichtigungen zu konfigurieren.

**So konfigurieren Sie lync-Benachrichtigungen**

1.  Klicken Sie im lync-Client auf das Symbol **Optionen** .

2.  Wählen Sie **Benachrichtigungen**aus.

3.  Aktivieren Sie unter **Allgemeine Benachrichtigungen**das Kontrollkästchen **Wenn jemand mich zu seiner Kontaktliste hinzufügt**.

4.  Wählen Sie unter Kontakte, die **lync nicht verwenden** **die Option Einladungen zulassen, aber alle anderen Kommunikationen blockieren**aus.

5.  Klicken Sie auf **OK** , um das Fenster Optionen zu schließen.

</div>

<span> </span>

</div>

</div>

</div>

