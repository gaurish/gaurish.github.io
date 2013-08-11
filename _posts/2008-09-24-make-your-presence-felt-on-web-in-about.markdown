---
author: gaurish
comments: true
date: 2008-09-24 14:48:00+00:00
layout: post
slug: make-your-presence-felt-on-web-in-about
title: Make your presence felt on the Web in about $8USD/Rs350INR
wordpress_id: 47
categories:
- Blogging
- Guides and Howtos
---

Do you want to have a Personal blog with a address of yourname.com and a personnel email id of [you@yourname.com](mailto:you@yourname.com) but you were shy because it costs too much very year. Check again now prices has fallen drastically it is possible to register a Domain for about $8USD/Rs.350INR per year.   

Now, many of you would like to ask "can I make your blog & email with just a domain?". The Answer is "No, you need other things".but good part is almost all other things needed for a personnel email & blog solution can be brought for FREE!.   

Here is the list of things we would be needing:-  

1) **.Com or any other **[**gTLD**](http://en.wikipedia.org/wiki/GTLD)** with Managed DNS service**: you can buy a domain from any [ICANN](http://en.wikipedia.org/wiki/ICANN) accredited registrar but I would recommend buying from namecheap.com as you also get ability to create CNAME,MX records, which need for brought separately for all other hosts. although Namecheap.com says Price at$9.29USD but it can be reduced to $8.41 by using a Coupon code:_BACK2SCHOOL_(Source:[Retailmenot](http://www.retailmenot.com/view/namecheap.com)). if you have already brought a domain from a different registrar and it didn't give Managed DNS. you can use [FreeDNS](http://freedns.afraid.org/) service for no extra charge.  

2) **Google Account:** for Blogspot blogging service. Mostly Likely you would be having a Google account, if not then [create one](https://www.google.com/accounts/NewAccount). After you created a Google account, Goto [Blogger.com/start](https://www.blogger.com/start) and create your own blog on Blogspot.com. choose available subdomain. if you already have a blog at Blogspot then no need to create a new one, you can transfer your existing blog to your new domain.  

  

**Note:**Instructions for configuring DNS are different for every registrar.  Hence,for clarity I would be using [FreeDNS](http://freedns.afraid.org/) service. it would enable me to give specific easy to understand, step by step. Since free service which is open to everyone without paying any charge.Therefore, you are encouraged to use this service.   



### PART-I

##### Setting up DNS Records

1) [Signup](http://freedns.afraid.org/signup/) for FreeDNS. Complete Registration by clicking on Activation link which would be sent to email address you provided at time of registration.Now your account activation is complete and you can proceed next step.  



[![](http://2.bp.blogspot.com/_wMAC6frBFdw/SNpOkCttyAI/AAAAAAAAAUY/e_P8yO-isq0/s320-R/Screenshot+-+9_24_2008+,+3_55_59+PM.png)](http://2.bp.blogspot.com/_wMAC6frBFdw/SNpOkCttyAI/AAAAAAAAAUY/0Dlkm4bF6es/s1600-h/Screenshot+-+9_24_2008+,+3_55_59+PM.png)

  

2) **Add Domain: **From the Homepage, Click on [Domains](http://freedns.afraid.org/domain/). your would be asked to login to your newly created account. Now click on [Add a Domain](http://freedns.afraid.org/domain/add.php)_._Now you should see a screen similar to what is given below. Enter the your Domain address, Choose Share State to _Private_ and click on **Submit**  



[![](http://4.bp.blogspot.com/_wMAC6frBFdw/SNpOmpwpGYI/AAAAAAAAAUg/7JjS9cnVCUI/s320-R/Screenshot+-+9_24_2008+,+4_09_18+PM.png)](http://4.bp.blogspot.com/_wMAC6frBFdw/SNpOmpwpGYI/AAAAAAAAAUg/fiEBm7UedTQ/s1600-h/Screenshot+-+9_24_2008+,+4_09_18+PM.png)

  

3) **Change NameServers: **Most likely you would receive a warning that your Domain is marked BROKEN. It is because you need change your Domain NameServer configuration. Instead of using default server, you have to change to FreeDns supplied nameservers which are:   



  * NS1.AFRAID.ORG


  * NS2.AFRAID.ORG


  * NS3.AFRAID.ORG


  * NS4.AFRAID.ORG

Changing Nameserver usually requires logging in to your Domain Control Panel and click on Option Named "Change Nameserver Records" or "Modify NameServer". If you need help you can contact your registrar and Perform a Google search. in search box enter "Change Nameserver <registrar name>". for example [Namecheap](http://www.google.co.in/search?q=change+nameserver+namecheap). A DNS change takes upto 24hrs after the change you should no longer see see the broken mark  



[![](http://1.bp.blogspot.com/_wMAC6frBFdw/SNpOpUL_RlI/AAAAAAAAAUo/cnX8QBqxsR0/s400-R/Screenshot+-+9_24_2008+,+4_12_20+PM.png)](http://1.bp.blogspot.com/_wMAC6frBFdw/SNpOpUL_RlI/AAAAAAAAAUo/tpYkgGZAVxc/s1600-h/Screenshot+-+9_24_2008+,+4_12_20+PM.png)

[![](http://4.bp.blogspot.com/_wMAC6frBFdw/SNpO0joBfWI/AAAAAAAAAUw/EP-YwBbJWCE/s320-R/Screenshot+-+9_24_2008+,+4_40_01+PM.png)](http://4.bp.blogspot.com/_wMAC6frBFdw/SNpO0joBfWI/AAAAAAAAAUw/CR_AG9pFrYU/s1600-h/Screenshot+-+9_24_2008+,+4_40_01+PM.png)

.  

  

4) Now Click on [Domains](http://freedns.afraid.org/domain/). you should get your newly added domain. to create DNS records click on Manage.  



[![](http://1.bp.blogspot.com/_wMAC6frBFdw/SNpO5yXNMXI/AAAAAAAAAU4/0sbPisr3o2I/s400-R/Screenshot+-+9_24_2008+,+4_41_55+PM.png)](http://1.bp.blogspot.com/_wMAC6frBFdw/SNpO5yXNMXI/AAAAAAAAAU4/xdmGOxp8Hxo/s1600-h/Screenshot+-+9_24_2008+,+4_41_55+PM.png)

  

5) In the next Screen, click on _ADD _to add a new subdomain.In enter the following values and click Save.  



[![](http://3.bp.blogspot.com/_wMAC6frBFdw/SNpO88AjIWI/AAAAAAAAAVA/32UcY3r6tWk/s320-R/Screenshot+-+9_24_2008+,+4_45_59+PM.png)](http://3.bp.blogspot.com/_wMAC6frBFdw/SNpO88AjIWI/AAAAAAAAAVA/6tToWdur1GY/s1600-h/Screenshot+-+9_24_2008+,+4_45_59+PM.png)

  * Type = CNAME


  * Subdomain = www


  * Destination = ghs.google.com



[![](http://1.bp.blogspot.com/_wMAC6frBFdw/SNpO--alAPI/AAAAAAAAAVI/n9Ezq3hQ9mI/s320-R/Screenshot+-+9_24_2008+,+4_50_17+PM.png)](http://1.bp.blogspot.com/_wMAC6frBFdw/SNpO--alAPI/AAAAAAAAAVI/N5y8kZ6eTjo/s1600-h/Screenshot+-+9_24_2008+,+4_50_17+PM.png)

  

6) Now click on yourdomain.com(remember there should not be any prefix  before it).In the Next screen Click on __Forward to a URL. __we should now create a Web Forward record.  



[![](http://2.bp.blogspot.com/_wMAC6frBFdw/SNpPCw_elEI/AAAAAAAAAVQ/pdt4l5XOazI/s320-R/Screenshot+-+9_24_2008+,+5_00_30+PM.png)](http://2.bp.blogspot.com/_wMAC6frBFdw/SNpPCw_elEI/AAAAAAAAAVQ/-nxqOR8HhM0/s1600-h/Screenshot+-+9_24_2008+,+5_00_30+PM.png)

[![](http://3.bp.blogspot.com/_wMAC6frBFdw/SNpPFjewP7I/AAAAAAAAAVY/K6pcBApLfVw/s320-R/Screenshot+-+9_24_2008+,+5_02_27+PM.png)](http://3.bp.blogspot.com/_wMAC6frBFdw/SNpPFjewP7I/AAAAAAAAAVY/uWs6Yqq_MYQ/s1600-h/Screenshot+-+9_24_2008+,+5_02_27+PM.png)

  

7) Leave the _Redirect From_ field as blank. In _Redirect To _Enter [http://www.YourDomain.com](http://www.yourdomain.com/). Please ensure presence to www. leave rest options at defaults and click on _Save_  



[![](http://3.bp.blogspot.com/_wMAC6frBFdw/SNpPKUvR8oI/AAAAAAAAAVg/qgXHix22djs/s400-R/Screenshot+-+9_24_2008+,+6_23_09+PM.png)](http://3.bp.blogspot.com/_wMAC6frBFdw/SNpPKUvR8oI/AAAAAAAAAVg/ydXSh3CzRZs/s1600-h/Screenshot+-+9_24_2008+,+6_23_09+PM.png)

  

8) Go Back to [Domains](http://freedns.afraid.org/domain/) & Manage(refer to step 4). Now we would change the MX record. click the link on which is has a value MX and 10:mail._yourdomain_.com  



[![](http://4.bp.blogspot.com/_wMAC6frBFdw/SNpPOEf_UJI/AAAAAAAAAVo/5xxEVMUQ6zs/s320-R/Screenshot+-+9_24_2008+,+6_30_58+PM.png)](http://4.bp.blogspot.com/_wMAC6frBFdw/SNpPOEf_UJI/AAAAAAAAAVo/rr_XswFSga8/s1600-h/Screenshot+-+9_24_2008+,+6_30_58+PM.png)

  

9) In the next screen for change MX record. and click on save  



  * Type = MX


  * Subdomain = 


  * Destination = 1:ASPMX.L.GOOGLE.COM



[![](http://3.bp.blogspot.com/_wMAC6frBFdw/SNpPQ8arqZI/AAAAAAAAAVw/PW_b6PIwOoE/s320-R/Screenshot+-+9_24_2008+,+6_38_33+PM.png)](http://3.bp.blogspot.com/_wMAC6frBFdw/SNpPQ8arqZI/AAAAAAAAAVw/I7H9jDdf2Tc/s1600-h/Screenshot+-+9_24_2008+,+6_38_33+PM.png)

  

10) We are Done with this part, your current screen should look similar to that of screenshot given below but the Domain name should be different and it should not appear broken as in my case. mine is showing broken   

because i am working on a imaginary Domain. for you if everything is fine it should show status as active.  



[![](http://2.bp.blogspot.com/_wMAC6frBFdw/SNpPVSo4GsI/AAAAAAAAAV4/Umr4ykReLBo/s320-R/Screenshot+-+9_24_2008+,+7_00_08+PM.png)](http://2.bp.blogspot.com/_wMAC6frBFdw/SNpPVSo4GsI/AAAAAAAAAV4/GZPjOzD5pY4/s1600-h/Screenshot+-+9_24_2008+,+7_00_08+PM.png)

  

11) (Optional)To check email you have to use [http://mail.google.com/a/yourdomain.com](http://mail.google.com/a/yourdomain.com). you want a shorter domain like [http://mail.yourdomain.com](http://mail.yourdomain.com/) then you have create a CNAME record mail.yourdomain.com pointing to ghs.google.com. Refer to Step 5 for more help  



[![](http://1.bp.blogspot.com/_wMAC6frBFdw/SNpPb04l71I/AAAAAAAAAWI/uSFbgK5Riqo/s320-R/Screenshot+-+9_24_2008+,+7_17_34+PM.png)](http://1.bp.blogspot.com/_wMAC6frBFdw/SNpPb04l71I/AAAAAAAAAWI/799TK-zAu-E/s1600-h/Screenshot+-+9_24_2008+,+7_17_34+PM.png)

  



### PART-II

##### Setting Up Email

1) [Signup](http://www.google.com/a/cpanel/domain/new) with Google Apps.Choose the [Standard Edition](http://www.google.com/apps/intl/en/business/editions.html). signup it pretty easy to figure out and you can read the inbuilt help in case of facing difficulty. After Sign you would be taken to your dashboard.  

  

2) **Verify domain ownership**:You in your Dashboard you will be get a Prompt "To activate Google Apps services you must verify that you own your domain - example.com". Click on Verify Domain Ownership.In Verification method choose create a CNAME record. Find the CNAME settings and enter the following as the CNAME value or alias: <verification string>.Set the CNAME destination to the following address:  

**google.com.**  Refer to PART-I Step 4-5, this time just enter the Verification string in place of www as sub domain.the Verification string would be different for every Domain.  



[![](http://2.bp.blogspot.com/_wMAC6frBFdw/SNpPYkgnZkI/AAAAAAAAAWA/yxIOatcsrqU/s400-R/Screenshot+-+9_24_2008+,+7_13_36+PM.png)](http://2.bp.blogspot.com/_wMAC6frBFdw/SNpPYkgnZkI/AAAAAAAAAWA/PLXuqmuZDO4/s1600-h/Screenshot+-+9_24_2008+,+7_13_36+PM.png)

  

  

3) **Active Email**:Now you need to active Email service by clicking on _Activate Email > I Have Completed these steps_._  _if everything is done correctly you can now proceed to adding more users in Dashboard.  



[![](http://4.bp.blogspot.com/_wMAC6frBFdw/SNpPhqiFyEI/AAAAAAAAAWY/GpPpa6wLIzc/s320-R/Screenshot+-+9_24_2008+,+7_22_44+PM.png)](http://4.bp.blogspot.com/_wMAC6frBFdw/SNpPhqiFyEI/AAAAAAAAAWY/zix1Jm52mN0/s1600-h/Screenshot+-+9_24_2008+,+7_22_44+PM.png)

[![](http://2.bp.blogspot.com/_wMAC6frBFdw/SNpPj9H6TnI/AAAAAAAAAWg/WzhqNq0PkQE/s320-R/Screenshot+-+9_24_2008+,+7_25_51+PM.png)](http://2.bp.blogspot.com/_wMAC6frBFdw/SNpPj9H6TnI/AAAAAAAAAWg/CfcJydW3pKE/s1600-h/Screenshot+-+9_24_2008+,+7_25_51+PM.png)

  



### PART-III

##### Setting Up your Blog

1)  Open [Blogger Dashboard](http://blogger.com/home). if you don't have a blogspot blog then get one  

2)  Under manage Blogs, click Settings    



[![](http://1.bp.blogspot.com/_wMAC6frBFdw/SNpOe8ZpAUI/AAAAAAAAAUI/UQHkcK6Q-jQ/s320-R/Screenshot+-+9_23_2008+,+8_50_53+PM.png)](http://1.bp.blogspot.com/_wMAC6frBFdw/SNpOe8ZpAUI/AAAAAAAAAUI/-Xc5HsEcDFI/s1600-h/Screenshot+-+9_23_2008+,+8_50_53+PM.png)

3) Navigate to Settings Tab Publishing Tab. Click on Switch to **Custom Domain**  

4) Now Publish your Blog at [www.yourdomain.com](http://www.yourdomain.com/) and click on Save. Also check the Box which says "Redirect gaurishsharma.com to www.gaurishsharma.com" and click on Save.  



[![](http://1.bp.blogspot.com/_wMAC6frBFdw/SNpPkypt0rI/AAAAAAAAAWo/asH2kTexJUo/s400-R/Screenshot+-+9_24_2008+,+7_37_05+PM.png)](http://1.bp.blogspot.com/_wMAC6frBFdw/SNpPkypt0rI/AAAAAAAAAWo/9KDRreEB2z0/s1600-h/Screenshot+-+9_24_2008+,+7_37_05+PM.png)

  

5) Wait for sometime for DNS changes to be replicated across the Internet Infrastructure. this normally takes upto 24hrs.   



### Final Thoughts

  * To make setup Process more easier you can Purchase Domain Directly through google.  Google Takes $10. payment is done via Google Checkout


  * If you want a Static Website instead of a Blog, then you can use Google Apps's Sites to Create one.


  * To check your mail you have to login at [http://mail.google.com/a/yourdomain.com](http://mail.google.com/a/yourdomain.com) or [http://mail.yourdomain.com](http://mail.yourdomain.com/) (If you created a Short URL)

Enjoy, your new CyberSpace !

Did you enjoy this Post?.Please give your feedback at contact at gaurishsharma.com.
Read more at GaurishSharma.com
