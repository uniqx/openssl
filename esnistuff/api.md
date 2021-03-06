# Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`define `[`MKESNIKEYS_BUFLEN`](#mk__esnikeys_8c_1a78e53e10a406675eace5e343d94db19f)            | just for laughs, won't be that long
`define `[`SSL_ESNI_STATUS_SUCCESS`](#esni_8h_1a6a4d94b18577a453e7ca65273c75b110)            | Success.
`define `[`SSL_ESNI_STATUS_FAILED`](#esni_8h_1aff48e6059acca5bd4a3f9f2a926e9ffd)            | Some internal error.
`define `[`SSL_ESNI_STATUS_BAD_CALL`](#esni_8h_1a182a797bad43060760194c701c882fd0)            | Required in/out arguments were NULL.
`define `[`SSL_ESNI_STATUS_NOT_TRIED`](#esni_8h_1ac754df41295244baf3b951e9cec0a1db)            | ESNI wasn't attempted.
`define `[`SSL_ESNI_STATUS_BAD_NAME`](#esni_8h_1a4019c4a8f415a42a213cc0c657d9986b)            | ESNI succeeded but the TLS server cert used didn't match the hidden service name.
`define `[`ESNI_F_BASE64_DECODE`](#esnierr_8h_1a9c57a1b191c8fc44f0c9d33e1fa63096)            | 
`define `[`ESNI_F_NEW_FROM_BASE64`](#esnierr_8h_1a2292c05f5c24b23849789eb87f20bb0c)            | 
`define `[`ESNI_F_ENC`](#esnierr_8h_1a5e1e464c2d05b71de95e455a341f477f)            | 
`define `[`ESNI_F_CHECKSUM_CHECK`](#esnierr_8h_1ac8cec6cf839fa6b361bc6f9abc001201)            | 
`define `[`ESNI_F_SERVER_ENABLE`](#esnierr_8h_1acad1a58b5647c362ed60ff908c36d5f6)            | 
`define `[`ESNI_F_DEC`](#esnierr_8h_1abfce120a6f075e1028bed584590a1c5d)            | 
`define `[`ESNI_R_BASE64_DECODE_ERROR`](#esnierr_8h_1a1c13aa91c93bd84f1f92101ddb9bc9eb)            | 
`define `[`ESNI_R_RR_DECODE_ERROR`](#esnierr_8h_1acc748e3e2af6dc12fead035b479c221f)            | 
`define `[`ESNI_R_NOT_IMPL`](#esnierr_8h_1aeb72e4451595e51885c8192c3c06e870)            | 
`define `[`ESNI_DEFAULT_PADDED`](#esni_8c_1a706a8b9ec3b00f59d60711d623c90d74)            | File: esni.c - the core implementation of drat-ietf-tls-esni-02 Author: [stephen.farrell@cs.tcd.ie](mailto:stephen.farrell@cs.tcd.ie) Date: 2018 December-ish.
`public static unsigned int `[`esni_cb`](#s__client_8c_1ae008482292dac8e7973f123dcea9324e)`(SSL * s,int index)`            | 
`public static unsigned int `[`esni_cb`](#s__server_8c_1ae008482292dac8e7973f123dcea9324e)`(SSL * s,int index)`            | print an ESNI structure
`public static size_t `[`esni_padding_cb`](#s__server_8c_1a2deb1d25456628e166cb5fbaa8f11bbf)`(SSL * s,int type,size_t len,void * arg)`            | @ brief pad Certificate and CertificateVerify messages
`public static int `[`ssl_esni_servername_cb`](#s__server_8c_1a454eca00c708c0f47fccc73616408b67)`(SSL * s,int * ad,void * arg)`            | a servername_cb that is ESNI aware
`public int `[`ERR_load_ESNI_strings`](#esnierr_8c_1ab6db8c60b35aacaa03550e6d9d9c2099)`(void)`            | Load strings into tables.
`public static void `[`so_esni_pbuf`](#mk__esnikeys_8c_1ae1bab08e2b36301f0c81f27d7ffb006b)`(char * msg,unsigned char * buf,size_t blen,int indent)`            | 
`public static int `[`esni_checksum_gen`](#mk__esnikeys_8c_1a32ec581cbe2fef728eca2951e596d25f)`(unsigned char * buf,size_t buf_len,unsigned char cksum)`            | generate the SHA256 checksum that should be in the DNS record
`public void `[`usage`](#mk__esnikeys_8c_1aa4817482b1728bf62acf8030cab9842c)`(char * prog)`            | 
`public static int `[`mk_esnikeys`](#mk__esnikeys_8c_1a9d11ac25babd35d36598edd0beab07c9)`(int argc,char ** argv)`            | Make an X25519 key pair and ESNIKeys structure for the public.
`public int `[`main`](#mk__esnikeys_8c_1a3c04138a5bfe5d72780bb7e82a18e627)`(int argc,char ** argv)`            | 
`public unsigned char * `[`wrap_keyshare`](#esni_8h_1a3dccd979a035c9ccb3c0d4fe49eb3a00)`(const unsigned char * keyshare,const size_t keyshare_len,const uint16_t curve_id,size_t * outlen)`            | wrap a "raw" key share in the relevant TLS presentation layer encoding
`public int `[`SSL_ESNI_enc`](#esni_8h_1a1059808bc7c121128c470de41e2dc304)`(`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esnikeys,size_t client_random_len,unsigned char * client_random,uint16_t curve_id,size_t client_keyshare_len,unsigned char * client_keyshare,`[`CLIENT_ESNI`](#esni_8h_1add3c7579c9f0d7bd5959b37f9c017461)` ** the_esni)`            | Do the client-side SNI encryption during a TLS handshake.
`public unsigned char * `[`SSL_ESNI_dec`](#esni_8h_1ae4af2d2173a5c3b1513a1dcd04e2e940)`(`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esni,size_t client_random_len,unsigned char * client_random,uint16_t curve_id,size_t client_keyshare_len,unsigned char * client_keyshare,size_t * encservername_len)`            | Server-side decryption during a TLS handshake.
`public void `[`SSL_ESNI_free`](#esni_8h_1a6d6ea1b22339efdc370e6cbf251b277d)`(`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esnikeys)`            | Memory management - free an SSL_ESNI.
`public void `[`CLIENT_ESNI_free`](#esni_8h_1a1a84158d3b21a24a5db6bac434a718dc)`(`[`CLIENT_ESNI`](#esni_8h_1add3c7579c9f0d7bd5959b37f9c017461)` * c)`            | Memory management - free a CLIENT_ESNI.
`public `[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * `[`SSL_ESNI_dup`](#esni_8h_1aff4a2acfe537bdf41b91eed11de4cc15)`(`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * orig,size_t nesni)`            | Duplicate the configuration related fields of an SSL_ESNI.
`public int `[`SSL_esni_checknames`](#esni_8h_1a55aedc0e921fd36dcc3327124f07da10)`(const char * encservername,const char * covername)`            | Make a basic check of names from CLI or API.
`public `[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * `[`SSL_ESNI_new_from_base64`](#esni_8h_1a672460fc59e13e81482f66c701d4bca7)`(const char * esnikeys)`            | Decode and check the value retieved from DNS (currently base64 encoded)
`public int `[`SSL_esni_enable`](#esni_8h_1a0ca4d48103270d6779cb2f6a608ba52a)`(SSL * s,const char * hidden,const char * cover,`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esni,int require_hidden_match)`            | Turn on SNI encryption for an (upcoming) TLS session.
`public int `[`SSL_esni_server_enable`](#esni_8h_1a0589fa7d65bf2263c361258876e0e67a)`(SSL_CTX * s,const char * esnikeyfile,const char * esnipubfile)`            | Turn on SNI Encryption, server-side.
`public int `[`SSL_ESNI_get_esni`](#esni_8h_1ac214a7933d6e5fa9e2be5218b9537a63)`(SSL * s,`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` ** esni)`            | Access an SSL_ESNI structure note - can include sensitive values!
`public int `[`SSL_ESNI_get_esni_ctx`](#esni_8h_1acd373a6c0dddd76f399e103e80f538cc)`(SSL_CTX * s,`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` ** esni)`            | Access an SSL_ESNI structure note - can include sensitive values!
`public int `[`SSL_ESNI_print`](#esni_8h_1acf8aa08880982952d1faee2fedd1bc67)`(BIO * out,`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esni)`            | Print the content of an SSL_ESNI.
`public int `[`SSL_get_esni_status`](#esni_8h_1abc2468ba57b69ddaca0344481027d7a1)`(SSL * s,char ** hidden,char ** cover)`            | API to allow calling code know ESNI outcome, post-handshake.
`public int `[`SSL_ESNI_set_private`](#esni_8h_1a8df1af022d25fc0f7e72683b0bd4667f)`(`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esni,char * private_str)`            | Allows caller to set the ECDH private value for ESNI.
`public int `[`SSL_ESNI_set_nonce`](#esni_8h_1a0f48da79909334acee7b24dec440eb4c)`(`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esni,unsigned char * nonce,size_t nlen)`            | Allows caller to set the nonce value for ESNI.
`public int `[`ERR_load_ESNI_strings`](#esnierr_8h_1ab6db8c60b35aacaa03550e6d9d9c2099)`(void)`            | Load strings into tables.
`public static uint64_t `[`uint64_from_bytes`](#esni_8c_1a83d195ea944e970d225ac1554c88c3d4)`(unsigned char * buf)`            | map 8 bytes in n/w byte order from PACKET to a 64-bit time value
`public static int `[`esni_base64_decode`](#esni_8c_1a64c9d65c28e852557b2ac325335c6a83)`(const char * in,unsigned char ** out)`            | Decode from TXT RR to binary buffer.
`public static const SSL_CIPHER * `[`cs2sc`](#esni_8c_1a45c16ecbc68d6567bf9d4ef58bfdb46f)`(uint16_t ciphersuite)`            | 
`public void `[`ESNI_RECORD_free`](#esni_8c_1a2af97ba7f8ebc58e04391bc845f21811)`(`[`ESNI_RECORD`](#esni_8h_1ab29e08d24d0eac604e0d6783dfbf1758)` * er)`            | Free up an ENSI_RECORD.
`public void `[`SSL_ESNI_free`](#esni_8c_1a3a532dc18d8ea55c30b74529946f66c7)`(`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esni)`            | Free up an SSL_ESNI structure.
`public static int `[`esni_checksum_check`](#esni_8c_1a4c8d42c0081cae34740804bb9c4fc88b)`(unsigned char * buf,size_t buf_len)`            | Verify the SHA256 checksum that should be in the DNS record.
`public static unsigned char * `[`esni_make_rd`](#esni_8c_1a1a6df9cdee70887ac4c2492164155e83)`(const unsigned char * buf,const size_t blen,const EVP_MD * md,size_t * rd_len)`            | Hash the buffer as per the ciphersuite specified therein.
`public unsigned char * `[`wrap_keyshare`](#esni_8c_1a3dccd979a035c9ccb3c0d4fe49eb3a00)`(const unsigned char * keyshare,const size_t keyshare_len,const uint16_t curve_id,size_t * outlen)`            | wrap a "raw" key share in the relevant TLS presentation layer encoding
`public `[`ESNI_RECORD`](#esni_8h_1ab29e08d24d0eac604e0d6783dfbf1758)` * `[`SSL_ESNI_RECORD_new_from_binary`](#esni_8c_1a013c3c4172d63a489aa314d4c3d4542d)`(unsigned char * binbuf,size_t binblen)`            | Decod from binary to ESNI_RECORD.
`public static int `[`esni_make_se_from_er`](#esni_8c_1a1332a08e3b77da97cc9aef2efd50f904)`(`[`ESNI_RECORD`](#esni_8h_1ab29e08d24d0eac604e0d6783dfbf1758)` * er,`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * se,int server)`            | populate an SSL_ESNI from an ESNI_RECORD
`public `[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * `[`SSL_ESNI_new_from_base64`](#esni_8c_1a672460fc59e13e81482f66c701d4bca7)`(const char * esnikeys)`            | Decode from base64 TXT RR to SSL_ESNI.
`public static void `[`esni_pbuf`](#esni_8c_1ad619d10af828adf65d47682bdab514d1)`(BIO * out,char * msg,unsigned char * buf,size_t blen,int indent)`            | print a buffer nicely
`public int `[`SSL_ESNI_print`](#esni_8c_1acf8aa08880982952d1faee2fedd1bc67)`(BIO * out,`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esni)`            | Print out the DNS RR value(s)
`public static unsigned char * `[`esni_nonce`](#esni_8c_1a50f8ca970c2ceb308dbf23fd0410ee3b)`(size_t nl)`            | Make a 16 octet nonce for ESNI.
`public static unsigned char * `[`esni_pad`](#esni_8c_1a3e85b60a8ef53ff8670c54af6e376c40)`(char * name,unsigned int padded_len)`            | Pad an SNI before encryption with zeros on the right to the required length.
`public static unsigned char * `[`esni_hkdf_extract`](#esni_8c_1a9f76caa6f579de747d413ee3e809650d)`(unsigned char * secret,size_t slen,size_t * olen,const EVP_MD * md)`            | Local wrapper for HKDF-Extract(salt,IVM)=HMAC-Hash(salt,IKM) according to RFC5689.
`public static unsigned char * `[`esni_hkdf_expand_label`](#esni_8c_1a7dd32376e27d6c6aed533917093639e8)`(unsigned char * Zx,size_t Zx_len,const char * label,unsigned char * hash,size_t hash_len,size_t * expanded_len,const EVP_MD * md)`            | expand a label as per the I-D
`public static unsigned char * `[`esni_aead_enc`](#esni_8c_1a7a9797b7a757306ed1035009fa7d0694)`(unsigned char * key,size_t key_len,unsigned char * iv,size_t iv_len,unsigned char * aad,size_t aad_len,unsigned char * plain,size_t plain_len,unsigned char * tag,size_t tag_len,size_t * cipher_len,uint16_t ciph)`            | do the AEAD encryption as per the I-D
`public static unsigned char * `[`esni_aead_dec`](#esni_8c_1a870cb4460d44f015048426db48ad9446)`(unsigned char * key,size_t key_len,unsigned char * iv,size_t iv_len,unsigned char * aad,size_t aad_len,unsigned char * cipher,size_t cipher_len,size_t * plain_len,uint16_t ciph)`            | do the AEAD decryption as per the I-D
`public static int `[`makeesnicontenthash`](#esni_8c_1a52493599c778fa63f5254cd84e8ae464)`(`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esnikeys,int server)`            | given an SSL_ESNI create ESNIContent and hash that
`public static int `[`key_derivation`](#esni_8c_1a42f693ae84206906ae6ff8cd553434ac)`(`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esnikeys)`            | from Zx and ESNIContent, derive key, iv and aad
`public int `[`SSL_ESNI_enc`](#esni_8c_1a1059808bc7c121128c470de41e2dc304)`(`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esnikeys,size_t client_random_len,unsigned char * client_random,uint16_t curve_id,size_t client_keyshare_len,unsigned char * client_keyshare,`[`CLIENT_ESNI`](#esni_8h_1add3c7579c9f0d7bd5959b37f9c017461)` ** the_esni)`            | Do the client-side SNI encryption during a TLS handshake.
`public unsigned char * `[`SSL_ESNI_dec`](#esni_8c_1ae4af2d2173a5c3b1513a1dcd04e2e940)`(`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esni,size_t client_random_len,unsigned char * client_random,uint16_t curve_id,size_t client_keyshare_len,unsigned char * client_keyshare,size_t * encservername_len)`            | Attempt/do the serveri-side decryption during a TLS handshake.
`public int `[`SSL_esni_checknames`](#esni_8c_1a55aedc0e921fd36dcc3327124f07da10)`(const char * encservername,const char * covername)`            | Make a basic check of names from CLI or API.
`public int `[`SSL_esni_enable`](#esni_8c_1a0ca4d48103270d6779cb2f6a608ba52a)`(SSL * s,const char * hidden,const char * cover,`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esni,int require_hidden_match)`            | Turn on SNI encryption for an (upcoming) TLS session.
`public int `[`SSL_esni_server_enable`](#esni_8c_1aeef3e81451e59142e5cdec4f26c09fff)`(SSL_CTX * s,const char * esnikeyfile,const char * esnipubfile)`            | Turn on SNI Encryption, server-side.
`public int `[`SSL_get_esni_status`](#esni_8c_1abc2468ba57b69ddaca0344481027d7a1)`(SSL * s,char ** hidden,char ** cover)`            | API to allow calling code know ESNI outcome, post-handshake.
`public void `[`SSL_set_esni_callback`](#esni_8c_1ac4fbad870f00b5b6cb84629c4995be02)`(SSL * s,SSL_esni_client_cb_func f)`            | 
`public void `[`SSL_set_esni_callback_ctx`](#esni_8c_1a67ce35919f89b9259bb873b7702227ac)`(SSL_CTX * s,SSL_esni_client_cb_func f)`            | 
`public int `[`SSL_ESNI_get_esni`](#esni_8c_1ac214a7933d6e5fa9e2be5218b9537a63)`(SSL * s,`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` ** esni)`            | Access an SSL_ESNI structure note - can include sensitive values!
`public int `[`SSL_ESNI_get_esni_ctx`](#esni_8c_1acd373a6c0dddd76f399e103e80f538cc)`(SSL_CTX * s,`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` ** esni)`            | Access an SSL_ESNI structure note - can include sensitive values!
`public int `[`SSL_ESNI_set_private`](#esni_8c_1a8df1af022d25fc0f7e72683b0bd4667f)`(`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esni,char * private_str)`            | Allows caller to set the ECDH private value for ESNI.
`public int `[`SSL_ESNI_set_nonce`](#esni_8c_1a0f48da79909334acee7b24dec440eb4c)`(`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esni,unsigned char * nonce,size_t nlen)`            | Allows caller to set the nonce value for ESNI.
`public `[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * `[`SSL_ESNI_dup`](#esni_8c_1aff4a2acfe537bdf41b91eed11de4cc15)`(`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * orig,size_t nesni)`            | Duplicate the configuration related fields of an SSL_ESNI.
`public static int `[`init_esni`](#extensions_8c_1a07941fe88fcdb65271ad678cd41e7d57)`(SSL * s,unsigned int context)`            | Just note that esni is not yet done.
`public static int `[`final_esni`](#extensions_8c_1a4027805482e89339fd2870f852db4b4e)`(SSL * s,unsigned int context,int sent)`            | check result of esni and return error or ok
`public static EXT_RETURN `[`esni_server_name_fixup`](#extensions__clnt_8c_1a2454a14e823689509154ca3bfb4cdaea)`(SSL * s,WPACKET * pkt,unsigned int context,X509 * x,size_t chainidx)`            | Possibly do/don't send SNI if doing ESNI.
`public EXT_RETURN `[`tls_construct_ctos_esni`](#extensions__clnt_8c_1afca936de2d3ae315b5e8b8b200d17462)`(SSL * s,WPACKET * pkt,unsigned int context,X509 * x,size_t chainidx)`            | Create the ESNI extension for the ClientHello.
`public int `[`tls_parse_stoc_esni`](#extensions__clnt_8c_1ac388d56d20b4d3b507e56203f1c08303)`(SSL * s,PACKET * pkt,unsigned int context,X509 * x,size_t chainidx)`            | Parse and check the ESNI value returned in the EncryptedExtensions to make sure it has the nonce we sent in the ClientHello.
`public int `[`tls_parse_ctos_esni`](#extensions__srvr_8c_1a4a75b5940e39e1b5da10aefc8ed0ac69)`(SSL * s,PACKET * pkt,unsigned int context,X509 * x,size_t chainidx)`            | Decodes inbound ESNI extension into SSL_ESNI structure.
`public EXT_RETURN `[`tls_construct_stoc_esni`](#extensions__srvr_8c_1ae56ce4660abc014b273c5f743bc3eb63)`(SSL * s,WPACKET * pkt,unsigned int context,X509 * x,size_t chainidx)`            | If ESNI all went well, and we have a nonce then send that back.
`struct `[`client_esni_st`](#structclient__esni__st) | What we send in the esni CH extension:
`struct `[`esni_padding_sizes`](#structesni__padding__sizes) | Padding size info.
`struct `[`esni_record_st`](#structesni__record__st) | Representation of what goes in DNS.
`struct `[`ssl_esni_st`](#structssl__esni__st) | The ESNI data structure that's part of the SSL structure.

## Members

<p id="mk__esnikeys_8c_1a78e53e10a406675eace5e343d94db19f"><hr></p>

#### `define `[`MKESNIKEYS_BUFLEN`](#mk__esnikeys_8c_1a78e53e10a406675eace5e343d94db19f) 

just for laughs, won't be that long

<p id="esni_8h_1a6a4d94b18577a453e7ca65273c75b110"><hr></p>

#### `define `[`SSL_ESNI_STATUS_SUCCESS`](#esni_8h_1a6a4d94b18577a453e7ca65273c75b110) 

Success.

<p id="esni_8h_1aff48e6059acca5bd4a3f9f2a926e9ffd"><hr></p>

#### `define `[`SSL_ESNI_STATUS_FAILED`](#esni_8h_1aff48e6059acca5bd4a3f9f2a926e9ffd) 

Some internal error.

<p id="esni_8h_1a182a797bad43060760194c701c882fd0"><hr></p>

#### `define `[`SSL_ESNI_STATUS_BAD_CALL`](#esni_8h_1a182a797bad43060760194c701c882fd0) 

Required in/out arguments were NULL.

<p id="esni_8h_1ac754df41295244baf3b951e9cec0a1db"><hr></p>

#### `define `[`SSL_ESNI_STATUS_NOT_TRIED`](#esni_8h_1ac754df41295244baf3b951e9cec0a1db) 

ESNI wasn't attempted.

<p id="esni_8h_1a4019c4a8f415a42a213cc0c657d9986b"><hr></p>

#### `define `[`SSL_ESNI_STATUS_BAD_NAME`](#esni_8h_1a4019c4a8f415a42a213cc0c657d9986b) 

ESNI succeeded but the TLS server cert used didn't match the hidden service name.

<p id="esnierr_8h_1a9c57a1b191c8fc44f0c9d33e1fa63096"><hr></p>

#### `define `[`ESNI_F_BASE64_DECODE`](#esnierr_8h_1a9c57a1b191c8fc44f0c9d33e1fa63096) 

<p id="esnierr_8h_1a2292c05f5c24b23849789eb87f20bb0c"><hr></p>

#### `define `[`ESNI_F_NEW_FROM_BASE64`](#esnierr_8h_1a2292c05f5c24b23849789eb87f20bb0c) 

<p id="esnierr_8h_1a5e1e464c2d05b71de95e455a341f477f"><hr></p>

#### `define `[`ESNI_F_ENC`](#esnierr_8h_1a5e1e464c2d05b71de95e455a341f477f) 

<p id="esnierr_8h_1ac8cec6cf839fa6b361bc6f9abc001201"><hr></p>

#### `define `[`ESNI_F_CHECKSUM_CHECK`](#esnierr_8h_1ac8cec6cf839fa6b361bc6f9abc001201) 

<p id="esnierr_8h_1acad1a58b5647c362ed60ff908c36d5f6"><hr></p>

#### `define `[`ESNI_F_SERVER_ENABLE`](#esnierr_8h_1acad1a58b5647c362ed60ff908c36d5f6) 

<p id="esnierr_8h_1abfce120a6f075e1028bed584590a1c5d"><hr></p>

#### `define `[`ESNI_F_DEC`](#esnierr_8h_1abfce120a6f075e1028bed584590a1c5d) 

<p id="esnierr_8h_1a1c13aa91c93bd84f1f92101ddb9bc9eb"><hr></p>

#### `define `[`ESNI_R_BASE64_DECODE_ERROR`](#esnierr_8h_1a1c13aa91c93bd84f1f92101ddb9bc9eb) 

<p id="esnierr_8h_1acc748e3e2af6dc12fead035b479c221f"><hr></p>

#### `define `[`ESNI_R_RR_DECODE_ERROR`](#esnierr_8h_1acc748e3e2af6dc12fead035b479c221f) 

<p id="esnierr_8h_1aeb72e4451595e51885c8192c3c06e870"><hr></p>

#### `define `[`ESNI_R_NOT_IMPL`](#esnierr_8h_1aeb72e4451595e51885c8192c3c06e870) 

<p id="esni_8c_1a706a8b9ec3b00f59d60711d623c90d74"><hr></p>

#### `define `[`ESNI_DEFAULT_PADDED`](#esni_8c_1a706a8b9ec3b00f59d60711d623c90d74) 

File: esni.c - the core implementation of drat-ietf-tls-esni-02 Author: [stephen.farrell@cs.tcd.ie](mailto:stephen.farrell@cs.tcd.ie) Date: 2018 December-ish.

Handle padding - the server needs to do padding in case the certificate/key-size exposes the ESNI. But so can lots of the other application interactions, so to be at least a bit cautious, we'll also pad the crap out of everything on the client side (at least to see what happens:-) This could be over-ridden by the client appication if it wants by setting a callback via SSL_set_record_padding_callback We'll try set to 486 bytes, so that 3 plaintexts are likely to fit in a 1500 byte MTU. (That's a pretty arbitrary decision:-) TODO: test and see how this padding affects a real application as soon as we've integrated with oneWe'll pad all TLS plaintext to this size

<p id="s__client_8c_1ae008482292dac8e7973f123dcea9324e"><hr></p>

#### `public static unsigned int `[`esni_cb`](#s__client_8c_1ae008482292dac8e7973f123dcea9324e)`(SSL * s,int index)` 

<p id="s__server_8c_1ae008482292dac8e7973f123dcea9324e"><hr></p>

#### `public static unsigned int `[`esni_cb`](#s__server_8c_1ae008482292dac8e7973f123dcea9324e)`(SSL * s,int index)` 

print an ESNI structure

<p id="s__server_8c_1a2deb1d25456628e166cb5fbaa8f11bbf"><hr></p>

#### `public static size_t `[`esni_padding_cb`](#s__server_8c_1a2deb1d25456628e166cb5fbaa8f11bbf)`(SSL * s,int type,size_t len,void * arg)` 

@ brief pad Certificate and CertificateVerify messages

This is passed to SSL_CTX_set_record_padding_callback and pads the Certificate and CertificateVerify handshake messages to a size derived from the argument arg

#### Parameters
* `s` is the SSL connection 

* `len` is the plaintext length before padding 

* `arg` is a pointer to an [esni_padding_sizes](#structesni__padding__sizes) struct 

#### Returns
is the number of bytes of padding to add to the plaintext

<p id="s__server_8c_1a454eca00c708c0f47fccc73616408b67"><hr></p>

#### `public static int `[`ssl_esni_servername_cb`](#s__server_8c_1a454eca00c708c0f47fccc73616408b67)`(SSL * s,int * ad,void * arg)` 

a servername_cb that is ESNI aware

The COVER is the command line -servername But our ESNI is just named in the cert for the 2nd context (ctx2) and not on the command line. So we need to check if the supplied (E)SNI matches either and serve whichever is appropriate. X509_check_host is the way to do that, given an X509* pointer.

#### Parameters
* `s` is the SSL connection 

* `ad` is dunno 

* `arg` is a pointer to a tlsext 

#### Returns
1 or error

<p id="esnierr_8c_1ab6db8c60b35aacaa03550e6d9d9c2099"><hr></p>

#### `public int `[`ERR_load_ESNI_strings`](#esnierr_8c_1ab6db8c60b35aacaa03550e6d9d9c2099)`(void)` 

Load strings into tables.

#### Returns
1 for success, not 1 otherwise

<p id="mk__esnikeys_8c_1ae1bab08e2b36301f0c81f27d7ffb006b"><hr></p>

#### `public static void `[`so_esni_pbuf`](#mk__esnikeys_8c_1ae1bab08e2b36301f0c81f27d7ffb006b)`(char * msg,unsigned char * buf,size_t blen,int indent)` 

<p id="mk__esnikeys_8c_1a32ec581cbe2fef728eca2951e596d25f"><hr></p>

#### `public static int `[`esni_checksum_gen`](#mk__esnikeys_8c_1a32ec581cbe2fef728eca2951e596d25f)`(unsigned char * buf,size_t buf_len,unsigned char cksum)` 

generate the SHA256 checksum that should be in the DNS record

Fixed SHA256 hash in this case, we work on the offset here, (bytes 2 bytes then 4 checksum bytes then rest) with no other knowledge of the encoding.

#### Parameters
* `buf` is the buffer 

* `buf_len` is obvous 

#### Returns
1 for success, not 1 otherwise

<p id="mk__esnikeys_8c_1aa4817482b1728bf62acf8030cab9842c"><hr></p>

#### `public void `[`usage`](#mk__esnikeys_8c_1aa4817482b1728bf62acf8030cab9842c)`(char * prog)` 

<p id="mk__esnikeys_8c_1a9d11ac25babd35d36598edd0beab07c9"><hr></p>

#### `public static int `[`mk_esnikeys`](#mk__esnikeys_8c_1a9d11ac25babd35d36598edd0beab07c9)`(int argc,char ** argv)` 

Make an X25519 key pair and ESNIKeys structure for the public.

> Todo: TODO: write base 64 version of public as well 

TODO: check out NSS code to see if I can make same format private 

TODO: Decide if supporting private key re-use is even needed.

<p id="mk__esnikeys_8c_1a3c04138a5bfe5d72780bb7e82a18e627"><hr></p>

#### `public int `[`main`](#mk__esnikeys_8c_1a3c04138a5bfe5d72780bb7e82a18e627)`(int argc,char ** argv)` 

<p id="esni_8h_1a3dccd979a035c9ccb3c0d4fe49eb3a00"><hr></p>

#### `public unsigned char * `[`wrap_keyshare`](#esni_8h_1a3dccd979a035c9ccb3c0d4fe49eb3a00)`(const unsigned char * keyshare,const size_t keyshare_len,const uint16_t curve_id,size_t * outlen)` 

wrap a "raw" key share in the relevant TLS presentation layer encoding

Put the outer length and curve ID around a key share. This just exists because we do it a few times: for the ESNI client keyshare and for handshake client keyshare. The input keyshare is the e.g. 32 octets of a point on curve 25519 as used in X25519.

#### Parameters
* `keyshare` is the input keyshare which'd be 32 octets for x25519 

* `keyshare_len` is the length of the above (0x20 for x25519) 

* `curve_id` is the IANA registered value for the curve e.g. 0x1d for X25519 

* `outlen` is the length of the encoded version of the above 

#### Returns
is NULL (on error) or a pointer to the encoded version buffer

Put the outer length and curve ID around a key share. This just exists because we do it twice: for the ESNI client keyshare and for handshake client keyshare. The input keyshare is the e.g. 32 octets of a point on curve 25519 as used in X25519. There's no magic here, it's just that this code recurs in handling ESNI. Theere might be some existing API to use that'd be better.

#### Parameters
* `keyshare` is the input keyshare which'd be 32 octets for x25519 

* `keyshare_len` is the length of the above (0x20 for x25519) 

* `curve_id` is the IANA registered value for the curve e.g. 0x1d for X25519 

* `outlen` is the length of the encoded version of the above 

#### Returns
is NULL (on error) or a pointer to the encoded version buffer

<p id="esni_8h_1a1059808bc7c121128c470de41e2dc304"><hr></p>

#### `public int `[`SSL_ESNI_enc`](#esni_8h_1a1059808bc7c121128c470de41e2dc304)`(`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esnikeys,size_t client_random_len,unsigned char * client_random,uint16_t curve_id,size_t client_keyshare_len,unsigned char * client_keyshare,`[`CLIENT_ESNI`](#esni_8h_1add3c7579c9f0d7bd5959b37f9c017461)` ** the_esni)` 

Do the client-side SNI encryption during a TLS handshake.

This is an internal API called as part of the state machine dealing with this extension.

#### Parameters
* `esnikeys` is the SSL_ESNI structure 

* `client_random_len` is the number of bytes of 

* `client_random` being the TLS h/s client random 

* `curve_id` is the curve_id of the client keyshare 

* `client_keyshare_len` is the number of bytes of 

* `client_keyshare` is the h/s client keyshare 

#### Returns
1 for success, other otherwise

<p id="esni_8h_1ae4af2d2173a5c3b1513a1dcd04e2e940"><hr></p>

#### `public unsigned char * `[`SSL_ESNI_dec`](#esni_8h_1ae4af2d2173a5c3b1513a1dcd04e2e940)`(`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esni,size_t client_random_len,unsigned char * client_random,uint16_t curve_id,size_t client_keyshare_len,unsigned char * client_keyshare,size_t * encservername_len)` 

Server-side decryption during a TLS handshake.

This is the internal API called as part of the state machine dealing with this extension. Note that the decrypted server name is just a set of octets - there is no guarantee it's a DNS name or printable etc. (Same as with SNI generally.)

#### Parameters
* `esni` is the SSL_ESNI structure 

* `client_random_len` is the number of bytes of 

* `client_random` being the TLS h/s client random 

* `curve_id` is the curve_id of the client keyshare 

* `client_keyshare_len` is the number of bytes of 

* `client_keyshare` is the h/s client keyshare 

#### Returns
NULL for error, or the decrypted servername when it works

Server-side decryption during a TLS handshake.

This is the internal API called as part of the state machine dealing with this extension.

Note that the decrypted server name is just a set of octets - there is no guarantee it's a DNS name or printable etc. (Same as with SNI generally.)

#### Parameters
* `esni` is the SSL_ESNI structure 

* `client_random_len` is the number of bytes of 

* `client_random` being the TLS h/s client random 

* `curve_id` is the curve_id of the client keyshare 

* `client_keyshare_len` is the number of bytes of 

* `client_keyshare` is the h/s client keyshare 

#### Returns
NULL for error, or the decrypted servername when it works

<p id="esni_8h_1a6d6ea1b22339efdc370e6cbf251b277d"><hr></p>

#### `public void `[`SSL_ESNI_free`](#esni_8h_1a6d6ea1b22339efdc370e6cbf251b277d)`(`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esnikeys)` 

Memory management - free an SSL_ESNI.

Free everything within an SSL_ESNI. Note that the caller has to free the top level SSL_ESNI, IOW the pattern here is: SSL_ESNI_free(esnikeys); OPENSSL_free(esnikeys);

#### Parameters
* `esnikeys` is an SSL_ESNI structure

Memory management - free an SSL_ESNI.

Note that we don't free the top level, caller should do that This will free the CLIENT_ESNI structure contained in here.

#### Parameters
* `esni` a ptr to an SSL_ESNI str

<p id="esni_8h_1a1a84158d3b21a24a5db6bac434a718dc"><hr></p>

#### `public void `[`CLIENT_ESNI_free`](#esni_8h_1a1a84158d3b21a24a5db6bac434a718dc)`(`[`CLIENT_ESNI`](#esni_8h_1add3c7579c9f0d7bd5959b37f9c017461)` * c)` 

Memory management - free a CLIENT_ESNI.

This is called from within SSL_ESNI_free so isn't really needed externally at all.

#### Parameters
* `c` is a CLIENT_ESNI structure

<p id="esni_8h_1aff4a2acfe537bdf41b91eed11de4cc15"><hr></p>

#### `public `[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * `[`SSL_ESNI_dup`](#esni_8h_1aff4a2acfe537bdf41b91eed11de4cc15)`(`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * orig,size_t nesni)` 

Duplicate the configuration related fields of an SSL_ESNI.

This is needed to handle the SSL_CTX->SSL factory model in the server. Clients don't need this. There aren't too many fields populated when this is called - essentially just the ESNIKeys and the server private value. For the moment, we actually only deep-copy those.

#### Parameters
* `orig` is the input array of SSL_ESNI to be partly deep-copied 

* `nesni` is the number of elements in the array 

#### Returns
a partial deep-copy array or NULL if errors occur

<p id="esni_8h_1a55aedc0e921fd36dcc3327124f07da10"><hr></p>

#### `public int `[`SSL_esni_checknames`](#esni_8h_1a55aedc0e921fd36dcc3327124f07da10)`(const char * encservername,const char * covername)` 

Make a basic check of names from CLI or API.

Note: This may disappear as all the checks currently done would result in errors anyway. However, that could change, so we'll keep it for now.

#### Parameters
* `encservername` the hidden servie 

* `convername` the cleartext SNI to send (can be NULL if we don't want any) 

#### Returns
1 for success, other otherwise

<p id="esni_8h_1a672460fc59e13e81482f66c701d4bca7"><hr></p>

#### `public `[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * `[`SSL_ESNI_new_from_base64`](#esni_8h_1a672460fc59e13e81482f66c701d4bca7)`(const char * esnikeys)` 

Decode and check the value retieved from DNS (currently base64 encoded)

#### Parameters
* `esnikeys` is the base64 encoded value from DNS 

#### Returns
is an SSL_ESNI structure

Decode and check the value retieved from DNS (currently base64 encoded)

This is inspired by, but not the same as, SCT_new_from_base64 from crypto/ct/ct_b64.c

#### Parameters
* `esnikeys` is the base64 encoded ESNIKeys object 

#### Returns
is NULL (on error) or an SSL_ESNI structure

<p id="esni_8h_1a0ca4d48103270d6779cb2f6a608ba52a"><hr></p>

#### `public int `[`SSL_esni_enable`](#esni_8h_1a0ca4d48103270d6779cb2f6a608ba52a)`(SSL * s,const char * hidden,const char * cover,`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esni,int require_hidden_match)` 

Turn on SNI encryption for an (upcoming) TLS session.

#### Parameters
* `s` is the SSL context 

* `hidde` is the hidden service name 

* `cover` is the cleartext SNI name to use 

* `esni` is the SSL_ESNI structure 

* `require_hidden_match` say whether to require (==1) the TLS server cert matches the hidden name 

#### Returns
1 for success, other otherwise

<p id="esni_8h_1a0589fa7d65bf2263c361258876e0e67a"><hr></p>

#### `public int `[`SSL_esni_server_enable`](#esni_8h_1a0589fa7d65bf2263c361258876e0e67a)`(SSL_CTX * s,const char * esnikeyfile,const char * esnipubfile)` 

Turn on SNI Encryption, server-side.

When this works, the server will decrypt any ESNI seen in ClientHellos and subsequently treat those as if they had been send in cleartext SNI.

#### Parameters
* `s` is the SSL server context 

* `esnikeyfile` has the relevant (X25519) private key in PEM format 

* `esnipubfile` has the relevant (binary encoded, not base64) ESNIKeys structure 

#### Returns
1 for success, other otherwise

<p id="esni_8h_1ac214a7933d6e5fa9e2be5218b9537a63"><hr></p>

#### `public int `[`SSL_ESNI_get_esni`](#esni_8h_1ac214a7933d6e5fa9e2be5218b9537a63)`(SSL * s,`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` ** esni)` 

Access an SSL_ESNI structure note - can include sensitive values!

#### Parameters
* `s` is a an SSL structure, as used on TLS client 

* `esni` is an SSL_ESNI structure 

#### Returns
1 for success, anything else for failure

<p id="esni_8h_1acd373a6c0dddd76f399e103e80f538cc"><hr></p>

#### `public int `[`SSL_ESNI_get_esni_ctx`](#esni_8h_1acd373a6c0dddd76f399e103e80f538cc)`(SSL_CTX * s,`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` ** esni)` 

Access an SSL_ESNI structure note - can include sensitive values!

#### Parameters
* `s` is a an SSL_CTX structure, as used on TLS server 

* `esni` is an SSL_ESNI structure 

#### Returns
0 for failure, non-zero is the number of SSL_ESNI in the array

<p id="esni_8h_1acf8aa08880982952d1faee2fedd1bc67"><hr></p>

#### `public int `[`SSL_ESNI_print`](#esni_8h_1acf8aa08880982952d1faee2fedd1bc67)`(BIO * out,`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esni)` 

Print the content of an SSL_ESNI.

#### Parameters
* `out` is the BIO to use (e.g. stdout/whatever)  is an SSL_ESNI strucutre 

#### Returns
1 for success, anything else for failure

Print the content of an SSL_ESNI.

This is called via callback

<p id="esni_8h_1abc2468ba57b69ddaca0344481027d7a1"><hr></p>

#### `public int `[`SSL_get_esni_status`](#esni_8h_1abc2468ba57b69ddaca0344481027d7a1)`(SSL * s,char ** hidden,char ** cover)` 

API to allow calling code know ESNI outcome, post-handshake.

This is intended to be called by applications after the TLS handshake is complete.

#### Parameters
* `s` The SSL context (if that's the right term) 

* `hidden` will be set to the address of the hidden service 

* `cover` will be set to the address of the hidden service 

#### Returns
1 for success, other otherwise

<p id="esni_8h_1a8df1af022d25fc0f7e72683b0bd4667f"><hr></p>

#### `public int `[`SSL_ESNI_set_private`](#esni_8h_1a8df1af022d25fc0f7e72683b0bd4667f)`(`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esni,char * private_str)` 

Allows caller to set the ECDH private value for ESNI.

This is intended to only be used for interop testing - what was useful was to grab the value from the NSS implemtation, force it into mine and see which of the derived values end up the same.

#### Parameters
* `esni` is the SSL_ESNI struture 

* `private_str` is an ASCII-hex encoded X25519 point (essentially a random 32 octet value:-) 

#### Returns
1 for success, other otherwise

<p id="esni_8h_1a0f48da79909334acee7b24dec440eb4c"><hr></p>

#### `public int `[`SSL_ESNI_set_nonce`](#esni_8h_1a0f48da79909334acee7b24dec440eb4c)`(`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esni,unsigned char * nonce,size_t nlen)` 

Allows caller to set the nonce value for ESNI.

This is intended to only be used for interop testing - what was useful was to grab the value from the NSS implemtation, force it into mine and see which of the derived values end up the same.

#### Parameters
* `esni` is the SSL_ESNI struture 

* `nonce` points to a buffer with the network byte order value  nlen is the size of the nonce buffer 

#### Returns
1 for success, other otherwise

<p id="esnierr_8h_1ab6db8c60b35aacaa03550e6d9d9c2099"><hr></p>

#### `public int `[`ERR_load_ESNI_strings`](#esnierr_8h_1ab6db8c60b35aacaa03550e6d9d9c2099)`(void)` 

Load strings into tables.

#### Returns
1 for success, not 1 otherwise

<p id="esni_8c_1a83d195ea944e970d225ac1554c88c3d4"><hr></p>

#### `public static uint64_t `[`uint64_from_bytes`](#esni_8c_1a83d195ea944e970d225ac1554c88c3d4)`(unsigned char * buf)` 

map 8 bytes in n/w byte order from PACKET to a 64-bit time value

> Todo: TODO: there must be code for this somewhere - find it

#### Parameters
* `buf` is a bit of the PACKET with the 8 octets of interest 

#### Returns
is the 64 bit value from those 8 octets

<p id="esni_8c_1a64c9d65c28e852557b2ac325335c6a83"><hr></p>

#### `public static int `[`esni_base64_decode`](#esni_8c_1a64c9d65c28e852557b2ac325335c6a83)`(const char * in,unsigned char ** out)` 

Decode from TXT RR to binary buffer.

This is the exact same as ct_base64_decode from crypto/ct/ct_b64.c which function is declared static but could otherwise be re-used. Returns -1 for error or length of decoded buffer length otherwise (wasn't clear to me at first glance). Possible future change: re-use the ct code by exporting it.

Decodes the base64 string |in| into |out|. A new string will be malloc'd and assigned to |out|. This will be owned by the caller. Do not provide a pre-allocated string in |out|. 
#### Parameters
* `in` is the base64 encoded string 

* `out` is the binary equivalent 

#### Returns
is the number of octets in |out| if successful, <=0 for failure

<p id="esni_8c_1a45c16ecbc68d6567bf9d4ef58bfdb46f"><hr></p>

#### `public static const SSL_CIPHER * `[`cs2sc`](#esni_8c_1a45c16ecbc68d6567bf9d4ef58bfdb46f)`(uint16_t ciphersuite)` 

<p id="esni_8c_1a2af97ba7f8ebc58e04391bc845f21811"><hr></p>

#### `public void `[`ESNI_RECORD_free`](#esni_8c_1a2af97ba7f8ebc58e04391bc845f21811)`(`[`ESNI_RECORD`](#esni_8h_1ab29e08d24d0eac604e0d6783dfbf1758)` * er)` 

Free up an ENSI_RECORD.

ESNI_RECORD is our struct for what's in the DNS

er is a pointer to the record

<p id="esni_8c_1a3a532dc18d8ea55c30b74529946f66c7"><hr></p>

#### `public void `[`SSL_ESNI_free`](#esni_8c_1a3a532dc18d8ea55c30b74529946f66c7)`(`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esni)` 

Free up an SSL_ESNI structure.

Memory management - free an SSL_ESNI.

Note that we don't free the top level, caller should do that This will free the CLIENT_ESNI structure contained in here.

#### Parameters
* `esni` a ptr to an SSL_ESNI str

<p id="esni_8c_1a4c8d42c0081cae34740804bb9c4fc88b"><hr></p>

#### `public static int `[`esni_checksum_check`](#esni_8c_1a4c8d42c0081cae34740804bb9c4fc88b)`(unsigned char * buf,size_t buf_len)` 

Verify the SHA256 checksum that should be in the DNS record.

Fixed SHA256 hash in this case, we work on the offset here, (bytes 2 bytes then 4 checksum bytes then rest) with no other knowledge of the encoding.

#### Parameters
* `buf` is the buffer 

* `buf_len` is obvous 

#### Returns
1 for success, not 1 otherwise

<p id="esni_8c_1a1a6df9cdee70887ac4c2492164155e83"><hr></p>

#### `public static unsigned char * `[`esni_make_rd`](#esni_8c_1a1a6df9cdee70887ac4c2492164155e83)`(const unsigned char * buf,const size_t blen,const EVP_MD * md,size_t * rd_len)` 

Hash the buffer as per the ciphersuite specified therein.

Note that this isn't quite what the I-D says - It seems that NSS uses the entire buffer, incl. the version, so I've also done that as it works! Opened issue: [https://github.com/tlswg/draft-ietf-tls-esni/issues/119](https://github.com/tlswg/draft-ietf-tls-esni/issues/119)

#### Parameters
* `buf` is the input buffer 

* `blen` is the input buffer length 

* `md` is the hash function 

* `rd_len` is (a ptr to) the output hash length 

#### Returns
a pointer to the hash buffer allocated within the function or NULL on error

<p id="esni_8c_1a3dccd979a035c9ccb3c0d4fe49eb3a00"><hr></p>

#### `public unsigned char * `[`wrap_keyshare`](#esni_8c_1a3dccd979a035c9ccb3c0d4fe49eb3a00)`(const unsigned char * keyshare,const size_t keyshare_len,const uint16_t curve_id,size_t * outlen)` 

wrap a "raw" key share in the relevant TLS presentation layer encoding

Put the outer length and curve ID around a key share. This just exists because we do it twice: for the ESNI client keyshare and for handshake client keyshare. The input keyshare is the e.g. 32 octets of a point on curve 25519 as used in X25519. There's no magic here, it's just that this code recurs in handling ESNI. Theere might be some existing API to use that'd be better.

#### Parameters
* `keyshare` is the input keyshare which'd be 32 octets for x25519 

* `keyshare_len` is the length of the above (0x20 for x25519) 

* `curve_id` is the IANA registered value for the curve e.g. 0x1d for X25519 

* `outlen` is the length of the encoded version of the above 

#### Returns
is NULL (on error) or a pointer to the encoded version buffer

<p id="esni_8c_1a013c3c4172d63a489aa314d4c3d4542d"><hr></p>

#### `public `[`ESNI_RECORD`](#esni_8h_1ab29e08d24d0eac604e0d6783dfbf1758)` * `[`SSL_ESNI_RECORD_new_from_binary`](#esni_8c_1a013c3c4172d63a489aa314d4c3d4542d)`(unsigned char * binbuf,size_t binblen)` 

Decod from binary to ESNI_RECORD.

#### Parameters
* `binbuf` is the buffer with the encoding 

* `binblen` is the length of binbunf 

#### Returns
NULL on error, or an ESNI_RECORD structure

<p id="esni_8c_1a1332a08e3b77da97cc9aef2efd50f904"><hr></p>

#### `public static int `[`esni_make_se_from_er`](#esni_8c_1a1332a08e3b77da97cc9aef2efd50f904)`(`[`ESNI_RECORD`](#esni_8h_1ab29e08d24d0eac604e0d6783dfbf1758)` * er,`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * se,int server)` 

populate an SSL_ESNI from an ESNI_RECORD

This is used by both client and server in (almost) identical ways. Note that se->encoded_rr and se->encodded_rr_len must be set before calling this, but that's usually fine.

> Todo: TODO: handle >1 of the many things that can have >1 instance (maybe at a higher layer)

#### Parameters
* `er` is the ESNI_RECORD 

* `se` is the SSL_ESNI 

* `server` is 1 if we're a TLS server, 0 otherwise, (just in case there's a difference) 

#### Returns
1 for success, not 1 otherwise

<p id="esni_8c_1a672460fc59e13e81482f66c701d4bca7"><hr></p>

#### `public `[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * `[`SSL_ESNI_new_from_base64`](#esni_8c_1a672460fc59e13e81482f66c701d4bca7)`(const char * esnikeys)` 

Decode from base64 TXT RR to SSL_ESNI.

Decode and check the value retieved from DNS (currently base64 encoded)

This is inspired by, but not the same as, SCT_new_from_base64 from crypto/ct/ct_b64.c

#### Parameters
* `esnikeys` is the base64 encoded ESNIKeys object 

#### Returns
is NULL (on error) or an SSL_ESNI structure

<p id="esni_8c_1ad619d10af828adf65d47682bdab514d1"><hr></p>

#### `public static void `[`esni_pbuf`](#esni_8c_1ad619d10af828adf65d47682bdab514d1)`(BIO * out,char * msg,unsigned char * buf,size_t blen,int indent)` 

print a buffer nicely

This is used in SSL_ESNI_print

<p id="esni_8c_1acf8aa08880982952d1faee2fedd1bc67"><hr></p>

#### `public int `[`SSL_ESNI_print`](#esni_8c_1acf8aa08880982952d1faee2fedd1bc67)`(BIO * out,`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esni)` 

Print out the DNS RR value(s)

Print the content of an SSL_ESNI.

This is called via callback

<p id="esni_8c_1a50f8ca970c2ceb308dbf23fd0410ee3b"><hr></p>

#### `public static unsigned char * `[`esni_nonce`](#esni_8c_1a50f8ca970c2ceb308dbf23fd0410ee3b)`(size_t nl)` 

Make a 16 octet nonce for ESNI.

<p id="esni_8c_1a3e85b60a8ef53ff8670c54af6e376c40"><hr></p>

#### `public static unsigned char * `[`esni_pad`](#esni_8c_1a3e85b60a8ef53ff8670c54af6e376c40)`(char * name,unsigned int padded_len)` 

Pad an SNI before encryption with zeros on the right to the required length.

<p id="esni_8c_1a9f76caa6f579de747d413ee3e809650d"><hr></p>

#### `public static unsigned char * `[`esni_hkdf_extract`](#esni_8c_1a9f76caa6f579de747d413ee3e809650d)`(unsigned char * secret,size_t slen,size_t * olen,const EVP_MD * md)` 

Local wrapper for HKDF-Extract(salt,IVM)=HMAC-Hash(salt,IKM) according to RFC5689.

<p id="esni_8c_1a7dd32376e27d6c6aed533917093639e8"><hr></p>

#### `public static unsigned char * `[`esni_hkdf_expand_label`](#esni_8c_1a7dd32376e27d6c6aed533917093639e8)`(unsigned char * Zx,size_t Zx_len,const char * label,unsigned char * hash,size_t hash_len,size_t * expanded_len,const EVP_MD * md)` 

expand a label as per the I-D

> Todo: TODO: this and esni_hkdf_extract should be better integrated There are functions that can do this that require an `SSL *s` input and we should move to use those.

<p id="esni_8c_1a7a9797b7a757306ed1035009fa7d0694"><hr></p>

#### `public static unsigned char * `[`esni_aead_enc`](#esni_8c_1a7a9797b7a757306ed1035009fa7d0694)`(unsigned char * key,size_t key_len,unsigned char * iv,size_t iv_len,unsigned char * aad,size_t aad_len,unsigned char * plain,size_t plain_len,unsigned char * tag,size_t tag_len,size_t * cipher_len,uint16_t ciph)` 

do the AEAD encryption as per the I-D

Note: The tag output isn't really needed but was useful when I got the aad wrong at one stage to keep it for now. Most parameters obvious but...

#### Parameters
* `cipher_Len` is an output 

#### Returns
NULL (on error) or pointer to alloced buffer for ciphertext

<p id="esni_8c_1a870cb4460d44f015048426db48ad9446"><hr></p>

#### `public static unsigned char * `[`esni_aead_dec`](#esni_8c_1a870cb4460d44f015048426db48ad9446)`(unsigned char * key,size_t key_len,unsigned char * iv,size_t iv_len,unsigned char * aad,size_t aad_len,unsigned char * cipher,size_t cipher_len,size_t * plain_len,uint16_t ciph)` 

do the AEAD decryption as per the I-D

Note: The tag output isn't really needed but was useful when I got the aad wrong at one stage to keep it for now. 
#### Parameters
* `cipher_Len` is an output 

#### Returns
NULL (on error) or pointer to alloced buffer for plaintext

<p id="esni_8c_1a52493599c778fa63f5254cd84e8ae464"><hr></p>

#### `public static int `[`makeesnicontenthash`](#esni_8c_1a52493599c778fa63f5254cd84e8ae464)`(`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esnikeys,int server)` 

given an SSL_ESNI create ESNIContent and hash that

encode up TLS client's ESNI public keyshare (in a different part of the SSL_ESNI for client and server) and other parts of ESNIContents, and hash those

#### Parameters
* `esni` is the SSL_ESNI structure 

* `server` is 1 if on the server, 0 for client 

#### Returns
1 for success, other otherwise

<p id="esni_8c_1a42f693ae84206906ae6ff8cd553434ac"><hr></p>

#### `public static int `[`key_derivation`](#esni_8c_1a42f693ae84206906ae6ff8cd553434ac)`(`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esnikeys)` 

from Zx and ESNIContent, derive key, iv and aad

#### Parameters
* `esni` is the SSL_ESNI structure 

#### Returns
1 for success, other otherwise

<p id="esni_8c_1a1059808bc7c121128c470de41e2dc304"><hr></p>

#### `public int `[`SSL_ESNI_enc`](#esni_8c_1a1059808bc7c121128c470de41e2dc304)`(`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esnikeys,size_t client_random_len,unsigned char * client_random,uint16_t curve_id,size_t client_keyshare_len,unsigned char * client_keyshare,`[`CLIENT_ESNI`](#esni_8h_1add3c7579c9f0d7bd5959b37f9c017461)` ** the_esni)` 

Do the client-side SNI encryption during a TLS handshake.

This is an internal API called as part of the state machine dealing with this extension.

#### Parameters
* `esnikeys` is the SSL_ESNI structure 

* `client_random_len` is the number of bytes of 

* `client_random` being the TLS h/s client random 

* `curve_id` is the curve_id of the client keyshare 

* `client_keyshare_len` is the number of bytes of 

* `client_keyshare` is the h/s client keyshare 

#### Returns
1 for success, other otherwise

<p id="esni_8c_1ae4af2d2173a5c3b1513a1dcd04e2e940"><hr></p>

#### `public unsigned char * `[`SSL_ESNI_dec`](#esni_8c_1ae4af2d2173a5c3b1513a1dcd04e2e940)`(`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esni,size_t client_random_len,unsigned char * client_random,uint16_t curve_id,size_t client_keyshare_len,unsigned char * client_keyshare,size_t * encservername_len)` 

Attempt/do the serveri-side decryption during a TLS handshake.

Server-side decryption during a TLS handshake.

This is the internal API called as part of the state machine dealing with this extension.

Note that the decrypted server name is just a set of octets - there is no guarantee it's a DNS name or printable etc. (Same as with SNI generally.)

#### Parameters
* `esni` is the SSL_ESNI structure 

* `client_random_len` is the number of bytes of 

* `client_random` being the TLS h/s client random 

* `curve_id` is the curve_id of the client keyshare 

* `client_keyshare_len` is the number of bytes of 

* `client_keyshare` is the h/s client keyshare 

#### Returns
NULL for error, or the decrypted servername when it works

<p id="esni_8c_1a55aedc0e921fd36dcc3327124f07da10"><hr></p>

#### `public int `[`SSL_esni_checknames`](#esni_8c_1a55aedc0e921fd36dcc3327124f07da10)`(const char * encservername,const char * covername)` 

Make a basic check of names from CLI or API.

Note: This may disappear as all the checks currently done would result in errors anyway. However, that could change, so we'll keep it for now.

#### Parameters
* `encservername` the hidden servie 

* `convername` the cleartext SNI to send (can be NULL if we don't want any) 

#### Returns
1 for success, other otherwise

<p id="esni_8c_1a0ca4d48103270d6779cb2f6a608ba52a"><hr></p>

#### `public int `[`SSL_esni_enable`](#esni_8c_1a0ca4d48103270d6779cb2f6a608ba52a)`(SSL * s,const char * hidden,const char * cover,`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esni,int require_hidden_match)` 

Turn on SNI encryption for an (upcoming) TLS session.

#### Parameters
* `s` is the SSL context 

* `hidde` is the hidden service name 

* `cover` is the cleartext SNI name to use 

* `esni` is the SSL_ESNI structure 

* `require_hidden_match` say whether to require (==1) the TLS server cert matches the hidden name 

#### Returns
1 for success, other otherwise

<p id="esni_8c_1aeef3e81451e59142e5cdec4f26c09fff"><hr></p>

#### `public int `[`SSL_esni_server_enable`](#esni_8c_1aeef3e81451e59142e5cdec4f26c09fff)`(SSL_CTX * s,const char * esnikeyfile,const char * esnipubfile)` 

Turn on SNI Encryption, server-side.

When this works, the server will decrypt any ESNI seen in ClientHellos and subsequently treat those as if they had been send in cleartext SNI.

#### Parameters
* `s` is the SSL server context 

* `esnikeyfile` has the relevant (X25519) private key in PEM format 

* `esnipubfile` has the relevant (binary encoded, not base64) ESNIKeys structure 

#### Returns
1 for success, other otherwise

<p id="esni_8c_1abc2468ba57b69ddaca0344481027d7a1"><hr></p>

#### `public int `[`SSL_get_esni_status`](#esni_8c_1abc2468ba57b69ddaca0344481027d7a1)`(SSL * s,char ** hidden,char ** cover)` 

API to allow calling code know ESNI outcome, post-handshake.

This is intended to be called by applications after the TLS handshake is complete.

#### Parameters
* `s` The SSL context (if that's the right term) 

* `hidden` will be set to the address of the hidden service 

* `cover` will be set to the address of the hidden service 

#### Returns
1 for success, other otherwise

<p id="esni_8c_1ac4fbad870f00b5b6cb84629c4995be02"><hr></p>

#### `public void `[`SSL_set_esni_callback`](#esni_8c_1ac4fbad870f00b5b6cb84629c4995be02)`(SSL * s,SSL_esni_client_cb_func f)` 

<p id="esni_8c_1a67ce35919f89b9259bb873b7702227ac"><hr></p>

#### `public void `[`SSL_set_esni_callback_ctx`](#esni_8c_1a67ce35919f89b9259bb873b7702227ac)`(SSL_CTX * s,SSL_esni_client_cb_func f)` 

<p id="esni_8c_1ac214a7933d6e5fa9e2be5218b9537a63"><hr></p>

#### `public int `[`SSL_ESNI_get_esni`](#esni_8c_1ac214a7933d6e5fa9e2be5218b9537a63)`(SSL * s,`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` ** esni)` 

Access an SSL_ESNI structure note - can include sensitive values!

#### Parameters
* `s` is a an SSL structure, as used on TLS client 

* `esni` is an SSL_ESNI structure 

#### Returns
1 for success, anything else for failure

<p id="esni_8c_1acd373a6c0dddd76f399e103e80f538cc"><hr></p>

#### `public int `[`SSL_ESNI_get_esni_ctx`](#esni_8c_1acd373a6c0dddd76f399e103e80f538cc)`(SSL_CTX * s,`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` ** esni)` 

Access an SSL_ESNI structure note - can include sensitive values!

#### Parameters
* `s` is a an SSL_CTX structure, as used on TLS server 

* `esni` is an SSL_ESNI structure 

#### Returns
0 for failure, non-zero is the number of SSL_ESNI in the array

<p id="esni_8c_1a8df1af022d25fc0f7e72683b0bd4667f"><hr></p>

#### `public int `[`SSL_ESNI_set_private`](#esni_8c_1a8df1af022d25fc0f7e72683b0bd4667f)`(`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esni,char * private_str)` 

Allows caller to set the ECDH private value for ESNI.

This is intended to only be used for interop testing - what was useful was to grab the value from the NSS implemtation, force it into mine and see which of the derived values end up the same.

#### Parameters
* `esni` is the SSL_ESNI struture 

* `private_str` is an ASCII-hex encoded X25519 point (essentially a random 32 octet value:-) 

#### Returns
1 for success, other otherwise

<p id="esni_8c_1a0f48da79909334acee7b24dec440eb4c"><hr></p>

#### `public int `[`SSL_ESNI_set_nonce`](#esni_8c_1a0f48da79909334acee7b24dec440eb4c)`(`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * esni,unsigned char * nonce,size_t nlen)` 

Allows caller to set the nonce value for ESNI.

This is intended to only be used for interop testing - what was useful was to grab the value from the NSS implemtation, force it into mine and see which of the derived values end up the same.

#### Parameters
* `esni` is the SSL_ESNI struture 

* `nonce` points to a buffer with the network byte order value  nlen is the size of the nonce buffer 

#### Returns
1 for success, other otherwise

<p id="esni_8c_1aff4a2acfe537bdf41b91eed11de4cc15"><hr></p>

#### `public `[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * `[`SSL_ESNI_dup`](#esni_8c_1aff4a2acfe537bdf41b91eed11de4cc15)`(`[`SSL_ESNI`](#esni_8h_1afeadfe79a7d92e7978789cc1c4ee3e7f)` * orig,size_t nesni)` 

Duplicate the configuration related fields of an SSL_ESNI.

This is needed to handle the SSL_CTX->SSL factory model in the server. Clients don't need this. There aren't too many fields populated when this is called - essentially just the ESNIKeys and the server private value. For the moment, we actually only deep-copy those.

#### Parameters
* `orig` is the input array of SSL_ESNI to be partly deep-copied 

* `nesni` is the number of elements in the array 

#### Returns
a partial deep-copy array or NULL if errors occur

<p id="extensions_8c_1a07941fe88fcdb65271ad678cd41e7d57"><hr></p>

#### `public static int `[`init_esni`](#extensions_8c_1a07941fe88fcdb65271ad678cd41e7d57)`(SSL * s,unsigned int context)` 

Just note that esni is not yet done.

<p id="extensions_8c_1a4027805482e89339fd2870f852db4b4e"><hr></p>

#### `public static int `[`final_esni`](#extensions_8c_1a4027805482e89339fd2870f852db4b4e)`(SSL * s,unsigned int context,int sent)` 

check result of esni and return error or ok

<p id="extensions__clnt_8c_1a2454a14e823689509154ca3bfb4cdaea"><hr></p>

#### `public static EXT_RETURN `[`esni_server_name_fixup`](#extensions__clnt_8c_1a2454a14e823689509154ca3bfb4cdaea)`(SSL * s,WPACKET * pkt,unsigned int context,X509 * x,size_t chainidx)` 

Possibly do/don't send SNI if doing ESNI.

Check if s.ext.hostname == s.esni.covername and s.esni.covername != s.esni.encservername (which shouldn't happen ever but who knows...) If either test fails don't send server_name. That is, if we want to send ESNI, then we only send SNI if the covername was explicitly set and is the same as the SNI (that maybe got set via some weirdo application API that we couldn't change when ESNI enabling perhaps)

<p id="extensions__clnt_8c_1afca936de2d3ae315b5e8b8b200d17462"><hr></p>

#### `public EXT_RETURN `[`tls_construct_ctos_esni`](#extensions__clnt_8c_1afca936de2d3ae315b5e8b8b200d17462)`(SSL * s,WPACKET * pkt,unsigned int context,X509 * x,size_t chainidx)` 

Create the ESNI extension for the ClientHello.

This gets the TLS h/w values needed (client_random, curve_id and TLS h/s key_share) and then calls SSL_ESNI_enc and encodes the resulting CLIENT_ESNI into the ClientHello.

<p id="extensions__clnt_8c_1ac388d56d20b4d3b507e56203f1c08303"><hr></p>

#### `public int `[`tls_parse_stoc_esni`](#extensions__clnt_8c_1ac388d56d20b4d3b507e56203f1c08303)`(SSL * s,PACKET * pkt,unsigned int context,X509 * x,size_t chainidx)` 

Parse and check the ESNI value returned in the EncryptedExtensions to make sure it has the nonce we sent in the ClientHello.

This is just checking the nonce.

<p id="extensions__srvr_8c_1a4a75b5940e39e1b5da10aefc8ed0ac69"><hr></p>

#### `public int `[`tls_parse_ctos_esni`](#extensions__srvr_8c_1a4a75b5940e39e1b5da10aefc8ed0ac69)`(SSL * s,PACKET * pkt,unsigned int context,X509 * x,size_t chainidx)` 

Decodes inbound ESNI extension into SSL_ESNI structure.

The ESNI stuff:

    struct {
       CipherSuite suite; from c->ciphersuite (SSL_CIPHER)
       KeyShareEntry key_share; from c->encoded_keshare (buffer)
       opaque record_digest<0..2^16-1>; from c->record_digest (buffer)
       opaque encrypted_sni<0..2^16-1>; from c->encrypted_sni (buffer)
    } ClientEncryptedSNI;

Parse, decrypt etc inbound ESNI extension.

<p id="extensions__srvr_8c_1ae56ce4660abc014b273c5f743bc3eb63"><hr></p>

#### `public EXT_RETURN `[`tls_construct_stoc_esni`](#extensions__srvr_8c_1ae56ce4660abc014b273c5f743bc3eb63)`(SSL * s,WPACKET * pkt,unsigned int context,X509 * x,size_t chainidx)` 

If ESNI all went well, and we have a nonce then send that back.

Just do the biz... :-)

<p id="structclient__esni__st"><hr></p>

# struct `client_esni_st` 

What we send in the esni CH extension:

The TLS presentation language version is:

    struct {
        CipherSuite suite;
        KeyShareEntry key_share;
        opaque record_digest<0..2^16-1>;
        opaque encrypted_sni<0..2^16-1>;
    } ClientEncryptedSNI;

Fields encoded in extension, these are copies, (not malloc'd) of pointers elsewhere in SSL_ESNI. One of these is returned from SSL_ESNI_enc, and is also pointed to from the SSL_ESNI structure.

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public uint16_t `[`ciphersuite`](#structclient__esni__st_1a9e55dac79113ba355d329f86fbdb7f50) | 
`public size_t `[`encoded_keyshare_len`](#structclient__esni__st_1a5647ef9466b0de060a8fdbadeab16ca9) | 
`public unsigned char * `[`encoded_keyshare`](#structclient__esni__st_1ada7c87c8765f080c25255c336c8f3dd8) | 
`public size_t `[`record_digest_len`](#structclient__esni__st_1ab975fc71e1200e4e15462149377ea18c) | 
`public unsigned char * `[`record_digest`](#structclient__esni__st_1af3490c8abb917246296c8c7ce51106c3) | 
`public size_t `[`encrypted_sni_len`](#structclient__esni__st_1ae2811613d6126039a546db956858db5c) | 
`public unsigned char * `[`encrypted_sni`](#structclient__esni__st_1aafe13f76c23f8743e110c116eaaed174) | 

## Members

<p id="structclient__esni__st_1a9e55dac79113ba355d329f86fbdb7f50"><hr></p>

#### `public uint16_t `[`ciphersuite`](#structclient__esni__st_1a9e55dac79113ba355d329f86fbdb7f50) 

<p id="structclient__esni__st_1a5647ef9466b0de060a8fdbadeab16ca9"><hr></p>

#### `public size_t `[`encoded_keyshare_len`](#structclient__esni__st_1a5647ef9466b0de060a8fdbadeab16ca9) 

<p id="structclient__esni__st_1ada7c87c8765f080c25255c336c8f3dd8"><hr></p>

#### `public unsigned char * `[`encoded_keyshare`](#structclient__esni__st_1ada7c87c8765f080c25255c336c8f3dd8) 

<p id="structclient__esni__st_1ab975fc71e1200e4e15462149377ea18c"><hr></p>

#### `public size_t `[`record_digest_len`](#structclient__esni__st_1ab975fc71e1200e4e15462149377ea18c) 

<p id="structclient__esni__st_1af3490c8abb917246296c8c7ce51106c3"><hr></p>

#### `public unsigned char * `[`record_digest`](#structclient__esni__st_1af3490c8abb917246296c8c7ce51106c3) 

<p id="structclient__esni__st_1ae2811613d6126039a546db956858db5c"><hr></p>

#### `public size_t `[`encrypted_sni_len`](#structclient__esni__st_1ae2811613d6126039a546db956858db5c) 

<p id="structclient__esni__st_1aafe13f76c23f8743e110c116eaaed174"><hr></p>

#### `public unsigned char * `[`encrypted_sni`](#structclient__esni__st_1aafe13f76c23f8743e110c116eaaed174) 

<p id="structesni__padding__sizes"><hr></p>

# struct `esni_padding_sizes` 

Padding size info.

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public size_t `[`certpad`](#structesni__padding__sizes_1a8ea988832a757092b11f1b2d6acc8d98) | Certificate messages to be a multiple of this size.
`public size_t `[`certverifypad`](#structesni__padding__sizes_1ae573edaa1c0c0f2fc7aea357d606b83a) | CertificateVerify messages to be a multiple of this size.

## Members

<p id="structesni__padding__sizes_1a8ea988832a757092b11f1b2d6acc8d98"><hr></p>

#### `public size_t `[`certpad`](#structesni__padding__sizes_1a8ea988832a757092b11f1b2d6acc8d98) 

Certificate messages to be a multiple of this size.

<p id="structesni__padding__sizes_1ae573edaa1c0c0f2fc7aea357d606b83a"><hr></p>

#### `public size_t `[`certverifypad`](#structesni__padding__sizes_1ae573edaa1c0c0f2fc7aea357d606b83a) 

CertificateVerify messages to be a multiple of this size.

<p id="structesni__record__st"><hr></p>

# struct `esni_record_st` 

Representation of what goes in DNS.

This is from the -02 I-D, in TLS presentation language:

    struct {
        uint16 version;
        uint8 checksum[4];
        KeyShareEntry keys<4..2^16-1>;
        CipherSuite cipher_suites<2..2^16-2>;
        uint16 padded_length;
        uint64 not_before;
        uint64 not_after;
        Extension extensions<0..2^16-1>;
    } ESNIKeys;

Note that I don't like the above, but it's what we have to work with at the moment.

This structure is purely used when decoding the RR value and is then discarded (selected values mapped into the SSL_ESNI structure).

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public unsigned int `[`version`](#structesni__record__st_1aa3c5b36b02f8154f6ced8a36f04d25c3) | 
`public unsigned char `[`checksum`](#structesni__record__st_1a2280cfc2817e94b494a3e120a44c82b3) | 
`public unsigned int `[`nkeys`](#structesni__record__st_1a128d54ebb6abfe2494da42b5706795d3) | 
`public uint16_t * `[`group_ids`](#structesni__record__st_1a323df5cbace94f73e1bbf922fb3cf64d) | 
`public EVP_PKEY ** `[`keys`](#structesni__record__st_1abc46d13be54f79110778946df8defbc6) | 
`public size_t * `[`encoded_lens`](#structesni__record__st_1ac6ab8f5ea17c69c4bd4bf51be55e30d3) | 
`public unsigned char ** `[`encoded_keys`](#structesni__record__st_1abe59c6e8bf0ff07cb3e4f185fabe1b07) | 
`public size_t `[`nsuites`](#structesni__record__st_1a221e917cb9ad6f6501a57330d13e5084) | 
`public uint16_t * `[`ciphersuites`](#structesni__record__st_1ae6845bbe19a868942f0125cc4007e48c) | 
`public unsigned int `[`padded_length`](#structesni__record__st_1a4fa1f10a8635d5dfed501815f928570d) | 
`public uint64_t `[`not_before`](#structesni__record__st_1a4db76296d4da4dd2c202ced371859a29) | 
`public uint64_t `[`not_after`](#structesni__record__st_1ae9ee01b4d38d36242d8f4300d98416e9) | 
`public unsigned int `[`nexts`](#structesni__record__st_1ad0ae17a1a37af37fae9d8a70ea74a996) | 
`public unsigned int * `[`exttypes`](#structesni__record__st_1a12b5bdb880a6b035a62a62e297809ad0) | 
`public void ** `[`exts`](#structesni__record__st_1af8d605ba06bf8043967269ac36aff7c8) | 

## Members

<p id="structesni__record__st_1aa3c5b36b02f8154f6ced8a36f04d25c3"><hr></p>

#### `public unsigned int `[`version`](#structesni__record__st_1aa3c5b36b02f8154f6ced8a36f04d25c3) 

<p id="structesni__record__st_1a2280cfc2817e94b494a3e120a44c82b3"><hr></p>

#### `public unsigned char `[`checksum`](#structesni__record__st_1a2280cfc2817e94b494a3e120a44c82b3) 

<p id="structesni__record__st_1a128d54ebb6abfe2494da42b5706795d3"><hr></p>

#### `public unsigned int `[`nkeys`](#structesni__record__st_1a128d54ebb6abfe2494da42b5706795d3) 

<p id="structesni__record__st_1a323df5cbace94f73e1bbf922fb3cf64d"><hr></p>

#### `public uint16_t * `[`group_ids`](#structesni__record__st_1a323df5cbace94f73e1bbf922fb3cf64d) 

<p id="structesni__record__st_1abc46d13be54f79110778946df8defbc6"><hr></p>

#### `public EVP_PKEY ** `[`keys`](#structesni__record__st_1abc46d13be54f79110778946df8defbc6) 

<p id="structesni__record__st_1ac6ab8f5ea17c69c4bd4bf51be55e30d3"><hr></p>

#### `public size_t * `[`encoded_lens`](#structesni__record__st_1ac6ab8f5ea17c69c4bd4bf51be55e30d3) 

<p id="structesni__record__st_1abe59c6e8bf0ff07cb3e4f185fabe1b07"><hr></p>

#### `public unsigned char ** `[`encoded_keys`](#structesni__record__st_1abe59c6e8bf0ff07cb3e4f185fabe1b07) 

<p id="structesni__record__st_1a221e917cb9ad6f6501a57330d13e5084"><hr></p>

#### `public size_t `[`nsuites`](#structesni__record__st_1a221e917cb9ad6f6501a57330d13e5084) 

<p id="structesni__record__st_1ae6845bbe19a868942f0125cc4007e48c"><hr></p>

#### `public uint16_t * `[`ciphersuites`](#structesni__record__st_1ae6845bbe19a868942f0125cc4007e48c) 

<p id="structesni__record__st_1a4fa1f10a8635d5dfed501815f928570d"><hr></p>

#### `public unsigned int `[`padded_length`](#structesni__record__st_1a4fa1f10a8635d5dfed501815f928570d) 

<p id="structesni__record__st_1a4db76296d4da4dd2c202ced371859a29"><hr></p>

#### `public uint64_t `[`not_before`](#structesni__record__st_1a4db76296d4da4dd2c202ced371859a29) 

<p id="structesni__record__st_1ae9ee01b4d38d36242d8f4300d98416e9"><hr></p>

#### `public uint64_t `[`not_after`](#structesni__record__st_1ae9ee01b4d38d36242d8f4300d98416e9) 

<p id="structesni__record__st_1ad0ae17a1a37af37fae9d8a70ea74a996"><hr></p>

#### `public unsigned int `[`nexts`](#structesni__record__st_1ad0ae17a1a37af37fae9d8a70ea74a996) 

<p id="structesni__record__st_1a12b5bdb880a6b035a62a62e297809ad0"><hr></p>

#### `public unsigned int * `[`exttypes`](#structesni__record__st_1a12b5bdb880a6b035a62a62e297809ad0) 

<p id="structesni__record__st_1af8d605ba06bf8043967269ac36aff7c8"><hr></p>

#### `public void ** `[`exts`](#structesni__record__st_1af8d605ba06bf8043967269ac36aff7c8) 

<p id="structssl__esni__st"><hr></p>

# struct `ssl_esni_st` 

The ESNI data structure that's part of the SSL structure.

On the client-side, one of these is part of the SSL structure. On the server-side, an array of these is part of the SSL_CTX structure, and we match one of 'em to be part of the SSL structure when a handshake is in porgress. (Well, hopefully:-)

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public char * `[`encservername`](#structssl__esni__st_1a2468815c9c565e18fd3c3bbe8deb5ac9) | hidden server name
`public char * `[`covername`](#structssl__esni__st_1a97b71311959fbdb7cd424106c9e2afab) | cleartext SNI (can be NULL)
`public int `[`require_hidden_match`](#structssl__esni__st_1a37524b2d52a46fa9df7193a2efcae39c) | If 1 then SSL_esni_get_status will barf if hidden name doesn't match TLS server cert. If 0, don't care.
`public size_t `[`encoded_rr_len`](#structssl__esni__st_1a27ada5b21000aeb74ca5ed8e76bca329) | 
`public unsigned char * `[`encoded_rr`](#structssl__esni__st_1a71c8c509c7d198e8a719c65f99137f42) | Binary (base64 decoded) RR value.
`public size_t `[`rd_len`](#structssl__esni__st_1a14dda82e4a3ff57fe2dc856e67a2c971) | 
`public unsigned char * `[`rd`](#structssl__esni__st_1a40750765b83b53e6b12c24d580dc6894) | Hash of the above (record_digest), using the relevant hash from the ciphersuite.
`public uint16_t `[`ciphersuite`](#structssl__esni__st_1abc06fe1b51acac92401d48fee0c97d1b) | from ESNIKeys after selection of local preference
`public uint16_t `[`group_id`](#structssl__esni__st_1ac47e519775c29bd9129eba95cbed25f9) | our chosen group e.g. X25519
`public size_t `[`esni_peer_keyshare_len`](#structssl__esni__st_1a45018bd6c55f58e594463ce17e6e96bb) | 
`public unsigned char * `[`esni_peer_keyshare`](#structssl__esni__st_1a45058e28bb36447e277246e7d382e8cd) | the encoded peer's public value
`public EVP_PKEY * `[`esni_peer_pkey`](#structssl__esni__st_1ae309319de3d8979b8f650567511b5db9) | the peer public as a key
`public size_t `[`padded_length`](#structssl__esni__st_1adf84b36cfa57d84629cac876c5330ba8) | from ESNIKeys
`public uint64_t `[`not_before`](#structssl__esni__st_1a4cb0d34f50b80a38964af87c544f7ce9) | from ESNIKeys (not currently used)
`public uint64_t `[`not_after`](#structssl__esni__st_1ac6d2a892f59c287cc6ee7aa35f23c593) | from ESNIKeys (not currently used)
`public int `[`nexts`](#structssl__esni__st_1ad378e22df57746ad53996b3557ad8b84) | number of extensions (not yet supported so >0 => fail)
`public void ** `[`exts`](#structssl__esni__st_1a6a0a42a24377c80cb1d1d614e770df18) | extensions
`public size_t `[`nonce_len`](#structssl__esni__st_1aa3e7c7adffc576490b12cb397398e9e4) | 
`public unsigned char * `[`nonce`](#structssl__esni__st_1a1b1a621faf0c5661d399f74a15f53ff4) | Nonce we challenge server to respond with.
`public size_t `[`hs_cr_len`](#structssl__esni__st_1a60c77ce40536a46dd82d534e305c841d) | 
`public unsigned char * `[`hs_cr`](#structssl__esni__st_1a41cc4a76f8c5791c2d56cda576f99b2e) | Client random from TLS h/s.
`public size_t `[`hs_kse_len`](#structssl__esni__st_1aaa28d8aae330ffb7d54690362dbbd099) | 
`public unsigned char * `[`hs_kse`](#structssl__esni__st_1ace5b1a36ef299d60894e6c12fb87efa8) | Client key share from TLS h/s.
`public EVP_PKEY * `[`keyshare`](#structssl__esni__st_1a26fe847e4d6ef31e052388db50ea6dfe) | my own private keyshare to use with server's ESNI share
`public size_t `[`encoded_keyshare_len`](#structssl__esni__st_1a996ba562dc4023f24f5f7b9e06cf7ea9) | 
`public unsigned char * `[`encoded_keyshare`](#structssl__esni__st_1a4d01bbfec69faa47688893bf97c3d517) | my own public key share
`public size_t `[`hi_len`](#structssl__esni__st_1a736fa2d396148e03dda2b6f16bf2f2b3) | 
`public unsigned char * `[`hi`](#structssl__esni__st_1a4a90ef99a66189196461a24be3228e88) | ESNIContent encoded (hash input)
`public size_t `[`hash_len`](#structssl__esni__st_1adc8cd5f2e038050f8f8c943ce83a69e7) | 
`public unsigned char * `[`hash`](#structssl__esni__st_1a13aa60c6ec57e21c72f3ad9a08501de0) | hash of hi (encoded ESNIContent)
`public size_t `[`realSNI_len`](#structssl__esni__st_1a6908a094db5191657c7215fc53c07cac) | 
`public unsigned char * `[`realSNI`](#structssl__esni__st_1a13b4a4088c85d54354a4d0b762b6ecf1) | padded ESNI
`public size_t `[`Z_len`](#structssl__esni__st_1a7481a2e9fa19146dc73daa985ab48299) | 
`public unsigned char * `[`Z`](#structssl__esni__st_1a34834976fb049c9648199f4d5d30ce5a) | ECDH shared secret.
`public size_t `[`Zx_len`](#structssl__esni__st_1a32851db584691fef7515514c3633cd10) | 
`public unsigned char * `[`Zx`](#structssl__esni__st_1a0e7f1692a4a10d5f4379ba416dfc8f9b) | derived from Z as per I-D
`public size_t `[`key_len`](#structssl__esni__st_1a2ba57f56ad092ad7aa99d1bf13c7ba4f) | 
`public unsigned char * `[`key`](#structssl__esni__st_1a82a0329090f1e41c1f194b965649c578) | derived key
`public size_t `[`iv_len`](#structssl__esni__st_1a860a6a8162ff52d946e501f70cb8cab3) | 
`public unsigned char * `[`iv`](#structssl__esni__st_1a68620bc395b1faeefd4ff616c987a762) | derived iv
`public size_t `[`aad_len`](#structssl__esni__st_1a3293081d097ffe98ee954fad33da1527) | 
`public unsigned char * `[`aad`](#structssl__esni__st_1a047ff937dc8738a348c38a1430d2a748) | derived aad
`public size_t `[`plain_len`](#structssl__esni__st_1a16cf3490d5e685f020d4b0dfebae20b4) | 
`public unsigned char * `[`plain`](#structssl__esni__st_1a8138dff60c8e4b4aefa3fca687071c72) | plaintext value for ESNI
`public size_t `[`cipher_len`](#structssl__esni__st_1ad8cff17bc628d23a8f07f222faea037b) | 
`public unsigned char * `[`cipher`](#structssl__esni__st_1a19d1bfe34738bd14d62c5f98d25ed9d8) | ciphetext value of ESNI
`public size_t `[`tag_len`](#structssl__esni__st_1a422257e7b151614e7873443572e380af) | 
`public unsigned char * `[`tag`](#structssl__esni__st_1ae12ddfc5fb31d43b68c9febca9730e94) | GCM tag (already also in ciphertext)
`public `[`CLIENT_ESNI`](#esni_8h_1add3c7579c9f0d7bd5959b37f9c017461)` * `[`the_esni`](#structssl__esni__st_1acc1e4d390a3f6fc96c52a10cac4fd6c1) | the final outputs for the caller (note: not separately alloc'd)

## Members

<p id="structssl__esni__st_1a2468815c9c565e18fd3c3bbe8deb5ac9"><hr></p>

#### `public char * `[`encservername`](#structssl__esni__st_1a2468815c9c565e18fd3c3bbe8deb5ac9) 

hidden server name

<p id="structssl__esni__st_1a97b71311959fbdb7cd424106c9e2afab"><hr></p>

#### `public char * `[`covername`](#structssl__esni__st_1a97b71311959fbdb7cd424106c9e2afab) 

cleartext SNI (can be NULL)

<p id="structssl__esni__st_1a37524b2d52a46fa9df7193a2efcae39c"><hr></p>

#### `public int `[`require_hidden_match`](#structssl__esni__st_1a37524b2d52a46fa9df7193a2efcae39c) 

If 1 then SSL_esni_get_status will barf if hidden name doesn't match TLS server cert. If 0, don't care.

<p id="structssl__esni__st_1a27ada5b21000aeb74ca5ed8e76bca329"><hr></p>

#### `public size_t `[`encoded_rr_len`](#structssl__esni__st_1a27ada5b21000aeb74ca5ed8e76bca329) 

<p id="structssl__esni__st_1a71c8c509c7d198e8a719c65f99137f42"><hr></p>

#### `public unsigned char * `[`encoded_rr`](#structssl__esni__st_1a71c8c509c7d198e8a719c65f99137f42) 

Binary (base64 decoded) RR value.

<p id="structssl__esni__st_1a14dda82e4a3ff57fe2dc856e67a2c971"><hr></p>

#### `public size_t `[`rd_len`](#structssl__esni__st_1a14dda82e4a3ff57fe2dc856e67a2c971) 

<p id="structssl__esni__st_1a40750765b83b53e6b12c24d580dc6894"><hr></p>

#### `public unsigned char * `[`rd`](#structssl__esni__st_1a40750765b83b53e6b12c24d580dc6894) 

Hash of the above (record_digest), using the relevant hash from the ciphersuite.

<p id="structssl__esni__st_1abc06fe1b51acac92401d48fee0c97d1b"><hr></p>

#### `public uint16_t `[`ciphersuite`](#structssl__esni__st_1abc06fe1b51acac92401d48fee0c97d1b) 

from ESNIKeys after selection of local preference

<p id="structssl__esni__st_1ac47e519775c29bd9129eba95cbed25f9"><hr></p>

#### `public uint16_t `[`group_id`](#structssl__esni__st_1ac47e519775c29bd9129eba95cbed25f9) 

our chosen group e.g. X25519

<p id="structssl__esni__st_1a45018bd6c55f58e594463ce17e6e96bb"><hr></p>

#### `public size_t `[`esni_peer_keyshare_len`](#structssl__esni__st_1a45018bd6c55f58e594463ce17e6e96bb) 

<p id="structssl__esni__st_1a45058e28bb36447e277246e7d382e8cd"><hr></p>

#### `public unsigned char * `[`esni_peer_keyshare`](#structssl__esni__st_1a45058e28bb36447e277246e7d382e8cd) 

the encoded peer's public value

<p id="structssl__esni__st_1ae309319de3d8979b8f650567511b5db9"><hr></p>

#### `public EVP_PKEY * `[`esni_peer_pkey`](#structssl__esni__st_1ae309319de3d8979b8f650567511b5db9) 

the peer public as a key

<p id="structssl__esni__st_1adf84b36cfa57d84629cac876c5330ba8"><hr></p>

#### `public size_t `[`padded_length`](#structssl__esni__st_1adf84b36cfa57d84629cac876c5330ba8) 

from ESNIKeys

<p id="structssl__esni__st_1a4cb0d34f50b80a38964af87c544f7ce9"><hr></p>

#### `public uint64_t `[`not_before`](#structssl__esni__st_1a4cb0d34f50b80a38964af87c544f7ce9) 

from ESNIKeys (not currently used)

<p id="structssl__esni__st_1ac6d2a892f59c287cc6ee7aa35f23c593"><hr></p>

#### `public uint64_t `[`not_after`](#structssl__esni__st_1ac6d2a892f59c287cc6ee7aa35f23c593) 

from ESNIKeys (not currently used)

<p id="structssl__esni__st_1ad378e22df57746ad53996b3557ad8b84"><hr></p>

#### `public int `[`nexts`](#structssl__esni__st_1ad378e22df57746ad53996b3557ad8b84) 

number of extensions (not yet supported so >0 => fail)

<p id="structssl__esni__st_1a6a0a42a24377c80cb1d1d614e770df18"><hr></p>

#### `public void ** `[`exts`](#structssl__esni__st_1a6a0a42a24377c80cb1d1d614e770df18) 

extensions

<p id="structssl__esni__st_1aa3e7c7adffc576490b12cb397398e9e4"><hr></p>

#### `public size_t `[`nonce_len`](#structssl__esni__st_1aa3e7c7adffc576490b12cb397398e9e4) 

<p id="structssl__esni__st_1a1b1a621faf0c5661d399f74a15f53ff4"><hr></p>

#### `public unsigned char * `[`nonce`](#structssl__esni__st_1a1b1a621faf0c5661d399f74a15f53ff4) 

Nonce we challenge server to respond with.

<p id="structssl__esni__st_1a60c77ce40536a46dd82d534e305c841d"><hr></p>

#### `public size_t `[`hs_cr_len`](#structssl__esni__st_1a60c77ce40536a46dd82d534e305c841d) 

<p id="structssl__esni__st_1a41cc4a76f8c5791c2d56cda576f99b2e"><hr></p>

#### `public unsigned char * `[`hs_cr`](#structssl__esni__st_1a41cc4a76f8c5791c2d56cda576f99b2e) 

Client random from TLS h/s.

<p id="structssl__esni__st_1aaa28d8aae330ffb7d54690362dbbd099"><hr></p>

#### `public size_t `[`hs_kse_len`](#structssl__esni__st_1aaa28d8aae330ffb7d54690362dbbd099) 

<p id="structssl__esni__st_1ace5b1a36ef299d60894e6c12fb87efa8"><hr></p>

#### `public unsigned char * `[`hs_kse`](#structssl__esni__st_1ace5b1a36ef299d60894e6c12fb87efa8) 

Client key share from TLS h/s.

<p id="structssl__esni__st_1a26fe847e4d6ef31e052388db50ea6dfe"><hr></p>

#### `public EVP_PKEY * `[`keyshare`](#structssl__esni__st_1a26fe847e4d6ef31e052388db50ea6dfe) 

my own private keyshare to use with server's ESNI share

<p id="structssl__esni__st_1a996ba562dc4023f24f5f7b9e06cf7ea9"><hr></p>

#### `public size_t `[`encoded_keyshare_len`](#structssl__esni__st_1a996ba562dc4023f24f5f7b9e06cf7ea9) 

<p id="structssl__esni__st_1a4d01bbfec69faa47688893bf97c3d517"><hr></p>

#### `public unsigned char * `[`encoded_keyshare`](#structssl__esni__st_1a4d01bbfec69faa47688893bf97c3d517) 

my own public key share

<p id="structssl__esni__st_1a736fa2d396148e03dda2b6f16bf2f2b3"><hr></p>

#### `public size_t `[`hi_len`](#structssl__esni__st_1a736fa2d396148e03dda2b6f16bf2f2b3) 

<p id="structssl__esni__st_1a4a90ef99a66189196461a24be3228e88"><hr></p>

#### `public unsigned char * `[`hi`](#structssl__esni__st_1a4a90ef99a66189196461a24be3228e88) 

ESNIContent encoded (hash input)

<p id="structssl__esni__st_1adc8cd5f2e038050f8f8c943ce83a69e7"><hr></p>

#### `public size_t `[`hash_len`](#structssl__esni__st_1adc8cd5f2e038050f8f8c943ce83a69e7) 

<p id="structssl__esni__st_1a13aa60c6ec57e21c72f3ad9a08501de0"><hr></p>

#### `public unsigned char * `[`hash`](#structssl__esni__st_1a13aa60c6ec57e21c72f3ad9a08501de0) 

hash of hi (encoded ESNIContent)

<p id="structssl__esni__st_1a6908a094db5191657c7215fc53c07cac"><hr></p>

#### `public size_t `[`realSNI_len`](#structssl__esni__st_1a6908a094db5191657c7215fc53c07cac) 

<p id="structssl__esni__st_1a13b4a4088c85d54354a4d0b762b6ecf1"><hr></p>

#### `public unsigned char * `[`realSNI`](#structssl__esni__st_1a13b4a4088c85d54354a4d0b762b6ecf1) 

padded ESNI

<p id="structssl__esni__st_1a7481a2e9fa19146dc73daa985ab48299"><hr></p>

#### `public size_t `[`Z_len`](#structssl__esni__st_1a7481a2e9fa19146dc73daa985ab48299) 

<p id="structssl__esni__st_1a34834976fb049c9648199f4d5d30ce5a"><hr></p>

#### `public unsigned char * `[`Z`](#structssl__esni__st_1a34834976fb049c9648199f4d5d30ce5a) 

ECDH shared secret.

<p id="structssl__esni__st_1a32851db584691fef7515514c3633cd10"><hr></p>

#### `public size_t `[`Zx_len`](#structssl__esni__st_1a32851db584691fef7515514c3633cd10) 

<p id="structssl__esni__st_1a0e7f1692a4a10d5f4379ba416dfc8f9b"><hr></p>

#### `public unsigned char * `[`Zx`](#structssl__esni__st_1a0e7f1692a4a10d5f4379ba416dfc8f9b) 

derived from Z as per I-D

<p id="structssl__esni__st_1a2ba57f56ad092ad7aa99d1bf13c7ba4f"><hr></p>

#### `public size_t `[`key_len`](#structssl__esni__st_1a2ba57f56ad092ad7aa99d1bf13c7ba4f) 

<p id="structssl__esni__st_1a82a0329090f1e41c1f194b965649c578"><hr></p>

#### `public unsigned char * `[`key`](#structssl__esni__st_1a82a0329090f1e41c1f194b965649c578) 

derived key

<p id="structssl__esni__st_1a860a6a8162ff52d946e501f70cb8cab3"><hr></p>

#### `public size_t `[`iv_len`](#structssl__esni__st_1a860a6a8162ff52d946e501f70cb8cab3) 

<p id="structssl__esni__st_1a68620bc395b1faeefd4ff616c987a762"><hr></p>

#### `public unsigned char * `[`iv`](#structssl__esni__st_1a68620bc395b1faeefd4ff616c987a762) 

derived iv

<p id="structssl__esni__st_1a3293081d097ffe98ee954fad33da1527"><hr></p>

#### `public size_t `[`aad_len`](#structssl__esni__st_1a3293081d097ffe98ee954fad33da1527) 

<p id="structssl__esni__st_1a047ff937dc8738a348c38a1430d2a748"><hr></p>

#### `public unsigned char * `[`aad`](#structssl__esni__st_1a047ff937dc8738a348c38a1430d2a748) 

derived aad

<p id="structssl__esni__st_1a16cf3490d5e685f020d4b0dfebae20b4"><hr></p>

#### `public size_t `[`plain_len`](#structssl__esni__st_1a16cf3490d5e685f020d4b0dfebae20b4) 

<p id="structssl__esni__st_1a8138dff60c8e4b4aefa3fca687071c72"><hr></p>

#### `public unsigned char * `[`plain`](#structssl__esni__st_1a8138dff60c8e4b4aefa3fca687071c72) 

plaintext value for ESNI

<p id="structssl__esni__st_1ad8cff17bc628d23a8f07f222faea037b"><hr></p>

#### `public size_t `[`cipher_len`](#structssl__esni__st_1ad8cff17bc628d23a8f07f222faea037b) 

<p id="structssl__esni__st_1a19d1bfe34738bd14d62c5f98d25ed9d8"><hr></p>

#### `public unsigned char * `[`cipher`](#structssl__esni__st_1a19d1bfe34738bd14d62c5f98d25ed9d8) 

ciphetext value of ESNI

<p id="structssl__esni__st_1a422257e7b151614e7873443572e380af"><hr></p>

#### `public size_t `[`tag_len`](#structssl__esni__st_1a422257e7b151614e7873443572e380af) 

<p id="structssl__esni__st_1ae12ddfc5fb31d43b68c9febca9730e94"><hr></p>

#### `public unsigned char * `[`tag`](#structssl__esni__st_1ae12ddfc5fb31d43b68c9febca9730e94) 

GCM tag (already also in ciphertext)

<p id="structssl__esni__st_1acc1e4d390a3f6fc96c52a10cac4fd6c1"><hr></p>

#### `public `[`CLIENT_ESNI`](#esni_8h_1add3c7579c9f0d7bd5959b37f9c017461)` * `[`the_esni`](#structssl__esni__st_1acc1e4d390a3f6fc96c52a10cac4fd6c1) 

the final outputs for the caller (note: not separately alloc'd)

Generated by [Moxygen](https://sourcey.com/moxygen)