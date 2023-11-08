# Architecture

## Backend Architecture

```
📦 backend
|  |- 📂 common:
|  |  |- 📜 optimizer.py : what optimizer to use (ie: SGD or Adam for now)
|  |  |- 📜 ai_drive.py
|  |  |- 📜 preprocessing.py
|  |  |- 📜 default_datasets.py : store logic to load in default datasets from scikit-learn
|  |  |- 📜 dataset.py : read in the dataset through URL or file upload
|  |  |- 📜 email_notifier.py : Endpoint to send email notification of training results via API Gateway + AWS SES
|  |  |- 📜 utils.py : utility functions that could be helpful
|  |  |- 📜 constants.py : list of helpful constants
|  |  |- 📜 __init__.py
|  |  |- 📜 kernel.py
|  |  |- 📜 loss_functions.py : loss function enum
|  |- 📂 ml:
|  |  |- 📜 ml_trainer.py : train a classical machine learning learning model on the dataset
|  |  |- 📜 __init__.py
|  |  |- 📜 ml_model_parser.py
|  |- 📂 dl:
|  |  |- 📜 dl_model.py : torch model based on user specifications from drag and drop
|  |  |- 📜 dl_eval.py : Evaluation functions for deep learning models in Pytorch (eg: accuracy, loss, etc)
|  |  |- 📜 dl_trainer.py : train a deep learning model on the dataset
|  |  |- 📜 detection.py
|  |  |- 📜 __init__.py
|  |  |- 📜 dl_model_parser.py : parse the user specified pytorch model
|  |- 📂 aws_helpers:
|  |  |- 📂 dynamo_db_utils:
|  |  |  |- 📜 trainspace_db.py
|  |  |  |- 📜 DynamoUnitTests.md
|  |  |  |- 📜 constants.py : list of helpful constants
|  |  |  |- 📜 dynamo_db_utils.py
|  |  |  |- 📜 userprogress_db.py
|  |  |- 📜 __init__.py
|  |- 📜 middleware.py
|  |- 📜 poetry.lock
|  |- 📜 epoch_times.csv
|  |- 📜 pyproject.toml
|  |- 📜 data.csv : data csv file for use in the playground
|  |- 📜 __init__.py
|  |- 📜 app.py : run the backend (entrypoint script)
```

## Frontend Architecture

```
📦 frontend
|  |- 📂 public:
|  |  |- 📂 images:
|  |  |  |- 📂 wiki_images:
|  |  |  |  |- 📜 tanh_plot.png
|  |  |  |  |- 📜 avgpool_maxpool.gif
|  |  |  |  |- 📜 conv2d2.gif
|  |  |  |  |- 📜 conv2d.gif
|  |  |  |  |- 📜 sigmoid_equation.png
|  |  |  |  |- 📜 maxpool2d.gif
|  |  |  |  |- 📜 softmax_equation.png : PNG file of Softmax equation
|  |  |  |  |- 📜 batchnorm_diagram.png
|  |  |  |  |- 📜 dropout_diagram.png
|  |  |  |  |- 📜 tanh_equation.png
|  |  |  |- 📂 learn_mod_images:
|  |  |  |  |- 📜 neuron.png
|  |  |  |  |- 📜 tanhactivation.png
|  |  |  |  |- 📜 neuronWithEquation.png
|  |  |  |  |- 📜 sigmoidactivation.png
|  |  |  |  |- 📜 lossExampleTable.png
|  |  |  |  |- 📜 sigmoidfunction.png
|  |  |  |  |- 📜 lossExampleEquation.png
|  |  |  |  |- 📜 neuralnet.png
|  |  |  |  |- 📜 LeakyReLUactivation.png
|  |  |  |  |- 📜 ReLUactivation.png
|  |  |  |  |- 📜 robotImage.jpg
|  |  |  |  |- 📜 binarystepactivation.png
|  |  |  |  |- 📜 lossExample.png
|  |  |  |- 📂 logos:
|  |  |  |  |- 📂 dlp_branding:
|  |  |  |  |  |- 📜 dlp-logo.svg : DLP Logo, duplicate of files in public, but essential as the frontend can't read public
|  |  |  |  |  |- 📜 dlp-logo.png : DLP Logo, duplicate of files in public, but essential as the frontend can't read public
|  |  |  |  |- 📜 react-logo.png
|  |  |  |  |- 📜 google.png
|  |  |  |  |- 📜 pytorch-logo.png
|  |  |  |  |- 📜 pandas-logo.png
|  |  |  |  |- 📜 dsgt-logo-dark.png
|  |  |  |  |- 📜 dsgt-logo-light.png
|  |  |  |  |- 📜 python-logo.png
|  |  |  |  |- 📜 dsgt-logo-white-back.png
|  |  |  |  |- 📜 github.png
|  |  |  |  |- 📜 aws-logo.png
|  |  |  |  |- 📜 flask-logo.png
|  |  |  |- 📜 demo_video.gif : GIF tutorial of a simple classification training session
|  |  |- 📜 robots.txt
|  |  |- 📜 dlp-logo.ico : DLP Logo
|  |  |- 📜 index.html : Base HTML file that will be initially rendered
|  |  |- 📜 manifest.json : Default React file for choosing icon based on
|  |- 📂 .yarn:
|  |  |- 📂 cache:
|  |  |  |- 📜 utils-copy-error-npm-1.0.1-59cc963f2e-15b630e483.zip
|  |  |  |- 📜 @humanwhocodes-module-importer-npm-1.0.1-9d07ed2e4a-0fd22007db.zip
|  |  |  |- 📜 @firebase-app-check-types-npm-0.5.0-c65d0311de-39828d64e3.zip
|  |  |  |- 📜 @mapbox-point-geometry-npm-0.1.0-d0fd1852be-ed41c1ce01.zip
|  |  |  |- 📜 @types-d3-array-npm-3.0.5-bf76aa12ba-c0014042f7.zip
|  |  |  |- 📜 babel-plugin-macros-npm-3.1.0-320e781f4e-765de4abeb.zip
|  |  |  |- 📜 jest-util-npm-29.5.0-cf917d20f1-fd9212950d.zip
|  |  |  |- 📜 gl-util-npm-3.1.3-8f018a4061-f162585854.zip
|  |  |  |- 📜 w3c-keyname-npm-2.2.6-55cd4f6245-59a31d23ca.zip
|  |  |  |- 📜 needle-npm-2.9.1-f40e591726-746ae3a378.zip
|  |  |  |- 📜 @babel-helper-function-name-npm-7.21.0-a17ce5a05a-d63e63c3e0.zip
|  |  |  |- 📜 @emotion-weak-memoize-npm-0.3.0-705bdd075b-f43ef4c8b7.zip
|  |  |  |- 📜 webidl-conversions-npm-3.0.1-60310f6a2b-c92a0a6ab9.zip
|  |  |  |- 📜 glob-to-regexp-npm-0.4.1-cd697e0fc7-e795f4e8f0.zip
|  |  |  |- 📜 websocket-driver-npm-0.7.4-a72739da70-fffe5a33fe.zip
|  |  |  |- 📜 update-diff-npm-1.1.0-a5dd7d23e6-546400522d.zip
|  |  |  |- 📜 zustand-npm-4.3.9-c1730d0244-fc83d65391.zip
|  |  |  |- 📜 const-max-uint32-npm-1.0.2-d69bc4c393-cefa23afd2.zip
|  |  |  |- 📜 has-flag-npm-3.0.0-16ac11fe05-4a15638b45.zip
|  |  |  |- 📜 css.escape-npm-1.5.1-b24d2ba77a-f6d38088d8.zip
|  |  |  |- 📜 @firebase-firestore-compat-npm-0.3.5-dd72629298-c36fb82dbd.zip
|  |  |  |- 📜 weak-map-npm-1.0.8-752d38a0d7-ce030b3c6b.zip
|  |  |  |- 📜 acorn-jsx-npm-5.3.2-d7594599ea-c3d3b2a89c.zip
|  |  |  |- 📜 events-npm-3.3.0-c280bc7e48-f6f487ad21.zip
|  |  |  |- 📜 d3-transition-npm-3.0.1-9191e0faaa-cb1e6e018c.zip
|  |  |  |- 📜 classnames-npm-2.3.2-d2fdae468d-2c62199789.zip
|  |  |  |- 📜 is-plain-obj-npm-1.1.0-1046f64c0b-0ee0480779.zip
|  |  |  |- 📜 fastq-npm-1.15.0-1013f6514e-0170e6bfcd.zip
|  |  |  |- 📜 character-entities-npm-1.2.4-a5c359383c-e154571657.zip
|  |  |  |- 📜 jest-get-type-npm-29.4.3-790eefdb01-6ac7f2dde1.zip
|  |  |  |- 📜 resolve-npm-1.22.1-3980488690-07af5fc1e8.zip
|  |  |  |- 📜 which-boxed-primitive-npm-1.0.2-e214f9ae5a-53ce774c73.zip
|  |  |  |- 📜 locate-path-npm-6.0.0-06a1e4c528-72eb661788.zip
|  |  |  |- 📜 has-passive-events-npm-1.0.0-ab3ec0b80b-604b447817.zip
|  |  |  |- 📜 @fortawesome-fontawesome-svg-core-npm-6.4.2-530d31922b-0c0ecd9058.zip
|  |  |  |- 📜 slash-npm-3.0.0-b87de2279a-94a93fff61.zip
|  |  |  |- 📜 detect-kerning-npm-2.1.2-e1a21c233a-bffd569e6b.zip
|  |  |  |- 📜 vt-pbf-npm-3.1.3-6b659628e6-83375b7ffe.zip
|  |  |  |- 📜 lodash.memoize-npm-4.1.2-0e6250041f-9ff3942fee.zip
|  |  |  |- 📜 @babel-helper-annotate-as-pure-npm-7.18.6-36e25293d8-88ccd15ced.zip
|  |  |  |- 📜 string_decoder-npm-0.10.31-851f3f7302-fe00f8e303.zip
|  |  |  |- 📜 is-symbol-npm-1.0.4-eb9baac703-92805812ef.zip
|  |  |  |- 📜 balanced-match-npm-1.0.2-a53c126459-9706c088a2.zip
|  |  |  |- 📜 isarray-npm-2.0.5-4ba522212d-bd5bbe4104.zip
|  |  |  |- 📜 d3-collection-npm-1.0.7-3c04196100-9c6b910a9d.zip
|  |  |  |- 📜 is-float-array-npm-1.0.0-ed885accdb-d2943c9065.zip
|  |  |  |- 📜 ansi-styles-npm-4.3.0-245c7d42c7-513b44c3b2.zip
|  |  |  |- 📜 @types-d3-zoom-npm-3.0.3-8b6f48e5a4-1c828538e2.zip
|  |  |  |- 📜 @eslint-community-regexpp-npm-4.4.0-6bee7b2314-2d127af0c7.zip
|  |  |  |- 📜 is-blob-npm-2.1.0-9aa6e9b797-ce24917bf5.zip
|  |  |  |- 📜 @dnd-kit-accessibility-npm-3.0.1-78bf91a820-0afc2c0fce.zip
|  |  |  |- 📜 doctrine-npm-2.1.0-ac15d049b7-a45e277f7f.zip
|  |  |  |- 📜 @protobufjs-base64-npm-1.1.2-cd8ca6814a-67173ac34d.zip
|  |  |  |- 📜 @turf-meta-npm-6.5.0-66a9378eac-c6bb936aa9.zip
|  |  |  |- 📜 get-symbol-description-npm-1.0.0-9c95a4bc1f-9ceff8fe96.zip
|  |  |  |- 📜 react-hook-form-npm-7.43.9-3a3f4f3335-65b94de625.zip
|  |  |  |- 📜 react-chartjs-2-npm-5.2.0-03632f5179-ace702185b.zip
|  |  |  |- 📜 is-alphabetical-npm-1.0.4-94e2e7f984-6508cce44f.zip
|  |  |  |- 📜 normalize-svg-path-npm-0.1.0-b205e8a97f-acf31e84e7.zip
|  |  |  |- 📜 @protobufjs-path-npm-1.1.2-641d08de76-856eeb532b.zip
|  |  |  |- 📜 error-ex-npm-1.3.2-5654f80c0f-c1c2b8b65f.zip
|  |  |  |- 📜 string.prototype.matchall-npm-4.0.8-1feb1531b6-952da3a818.zip
|  |  |  |- 📜 @testing-library-jest-dom-npm-5.16.5-b6d1f4e02f-94911f901a.zip
|  |  |  |- 📜 react-select-npm-5.7.0-1bd3ca6f36-3d29f7bb6d.zip
|  |  |  |- 📜 minimatch-npm-3.1.2-9405269906-c154e56640.zip
|  |  |  |- 📜 @emotion-use-insertion-effect-with-fallbacks-npm-1.0.0-d02a7659c4-4f06a3b482.zip
|  |  |  |- 📜 word-wrap-npm-1.2.4-7a75a0d62c-8f1f2e0a39.zip
|  |  |  |- 📜 is-firefox-npm-1.0.3-706b9e684b-8d4800d680.zip
|  |  |  |- 📜 glsl-token-inject-block-npm-1.1.0-7d9ccc620c-a08aca0f06.zip
|  |  |  |- 📜 once-npm-1.3.3-595f0882a4-8e832de08b.zip
|  |  |  |- 📜 @types-hast-npm-2.3.4-7249cc0ece-fff47998f4.zip
|  |  |  |- 📜 @firebase-remote-config-npm-0.4.4-9d52212d46-08b40da1ce.zip
|  |  |  |- 📜 @types-yargs-parser-npm-21.0.0-c8a3b32c52-b2f4c8d12a.zip
|  |  |  |- 📜 @mui-material-npm-5.11.13-81a5e5534b-008e7e79bf.zip
|  |  |  |- 📜 @firebase-functions-npm-0.9.4-ce12dec944-e00c6eec9f.zip
|  |  |  |- 📜 css-color-keywords-npm-1.0.0-fc176df58b-8f125e3ad4.zip
|  |  |  |- 📜 call-bind-npm-1.0.2-c957124861-f8e31de9d1.zip
|  |  |  |- 📜 picomatch-npm-2.3.1-c782cfd986-050c865ce8.zip
|  |  |  |- 📜 @protobufjs-pool-npm-1.1.0-47a76f96a1-d6a34fbbd2.zip
|  |  |  |- 📜 safer-buffer-npm-2.1.2-8d5c0b705e-cab8f25ae6.zip
|  |  |  |- 📜 wrap-ansi-npm-7.0.0-ad6e1a0554-a790b846fd.zip
|  |  |  |- 📜 end-of-stream-npm-1.4.4-497fc6dee1-530a5a5a1e.zip
|  |  |  |- 📜 dtype-npm-2.0.0-5c3c475c6d-a8fcdf549e.zip
|  |  |  |- 📜 svg-arc-to-cubic-bezier-npm-3.2.0-06dd5e62ac-55bf17756d.zip
|  |  |  |- 📜 object-keys-npm-1.1.1-1bf2f1be93-b363c5e764.zip
|  |  |  |- 📜 validate.io-number-primitive-npm-1.0.0-14f328a43d-4a5c66ca9f.zip
|  |  |  |- 📜 kdbush-npm-3.0.0-3f45162b37-bc5fa43395.zip
|  |  |  |- 📜 reusify-npm-1.0.4-95ac4aec11-c3076ebcc2.zip
|  |  |  |- 📜 commander-npm-2.20.3-d8dcbaa39b-ab8c07884e.zip
|  |  |  |- 📜 @types-istanbul-reports-npm-3.0.1-770e825002-f1ad54bc68.zip
|  |  |  |- 📜 react-csv-npm-2.2.2-b5548c3e54-a6ffabd67f.zip
|  |  |  |- 📜 regl-line2d-npm-3.1.2-b7c976ed3e-aa15125c92.zip
|  |  |  |- 📜 validate.io-array-like-npm-1.0.2-ba7ada88aa-5a0cac3e3b.zip
|  |  |  |- 📜 @types-react-google-recaptcha-npm-2.1.5-1dd3815d5d-8d0fa9e2ad.zip
|  |  |  |- 📜 @babel-helper-environment-visitor-npm-7.18.9-9f5b3635a1-b25101f616.zip
|  |  |  |- 📜 js-yaml-npm-4.1.0-3606f32312-c7830dfd45.zip
|  |  |  |- 📜 @nodelib-fs.stat-npm-2.0.5-01f4dd3030-012480b5ca.zip
|  |  |  |- 📜 imurmurhash-npm-0.1.4-610c5068a0-7cae75c8cd.zip
|  |  |  |- 📜 @emotion-memoize-npm-0.8.0-c5dd451828-c87bb110b8.zip
|  |  |  |- 📜 @protobufjs-codegen-npm-2.0.4-36e188bbe6-59240c850b.zip
|  |  |  |- 📜 cross-spawn-npm-7.0.3-e4ff3e65b3-671cc7c728.zip
|  |  |  |- 📜 is-glob-npm-4.0.3-cb87bf1bdb-d381c1319f.zip
|  |  |  |- 📜 prelude-ls-npm-1.1.2-a0daac0886-c4867c8748.zip
|  |  |  |- 📜 mime-types-npm-2.1.35-dd9ea9f3e2-89a5b7f1de.zip
|  |  |  |- 📜 eslint-visitor-keys-npm-3.3.0-d329af7c8c-d59e68a7c5.zip
|  |  |  |- 📜 bootstrap-npm-5.2.3-7458283a23-0211805dec.zip
|  |  |  |- 📜 potpack-npm-1.0.2-5f717e5a63-9dfdbbce01.zip
|  |  |  |- 📜 @codemirror-lang-python-npm-6.1.2-fb7c51745d-e822a1236f.zip
|  |  |  |- 📜 @firebase-auth-interop-types-npm-0.2.1-242b1f6861-6b02996f24.zip
|  |  |  |- 📜 readable-stream-npm-2.3.8-67a94c2cb1-6564546703.zip
|  |  |  |- 📜 color-id-npm-1.1.0-f910378387-11590fcaa3.zip
|  |  |  |- 📜 is-typed-array-npm-1.1.10-fe4ef83cdc-aac6ecb59d.zip
|  |  |  |- 📜 falafel-npm-2.2.5-ffc1a62bce-bfd46e92bc.zip
|  |  |  |- 📜 @floating-ui-dom-npm-1.2.4-950afe60a4-5c24a2e8f0.zip
|  |  |  |- 📜 warning-npm-4.0.3-291e921d6d-4f2cb6a957.zip
|  |  |  |- 📜 get-stream-npm-6.0.1-83e51a4642-e04ecece32.zip
|  |  |  |- 📜 validate.io-buffer-npm-1.0.2-fb6d9f0670-b7aaba2495.zip
|  |  |  |- 📜 comma-separated-tokens-npm-1.0.8-00dbbf3418-0adcb07174.zip
|  |  |  |- 📜 gl-mat4-npm-1.2.0-46b2e28ff3-04fb6b7a34.zip
|  |  |  |- 📜 @types-d3-brush-npm-3.0.2-cfb88a6964-5a539f94ff.zip
|  |  |  |- 📜 @protobufjs-float-npm-1.0.2-5678f64d08-5781e12412.zip
|  |  |  |- 📜 react-datepicker-npm-2.16.0-95827c9b09-ce74eb6dab.zip
|  |  |  |- 📜 @fortawesome-free-solid-svg-icons-npm-6.4.2-c582f5c032-4a36500499.zip
|  |  |  |- 📜 rc-progress-npm-3.4.1-52237c37e9-d4dce5231e.zip
|  |  |  |- 📜 acorn-npm-7.4.1-f450b4646c-1860f23c21.zip
|  |  |  |- 📜 validate.io-nonnegative-integer-npm-1.0.0-898ed9d016-537485682c.zip
|  |  |  |- 📜 @emotion-is-prop-valid-npm-1.2.0-332d343e3d-cc7a19850a.zip
|  |  |  |- 📜 semver-npm-6.3.1-bcba31fdbe-ae47d06de2.zip
|  |  |  |- 📜 @mapbox-tiny-sdf-npm-1.2.5-629b4030d6-d4cfd700c8.zip
|  |  |  |- 📜 typedarray-npm-0.0.6-37638b2241-33b39f3d0e.zip
|  |  |  |- 📜 axios-npm-0.26.1-a6641ce4e3-d9eb58ff4b.zip
|  |  |  |- 📜 supercluster-npm-7.1.5-369b0b6fb2-6986323887.zip
|  |  |  |- 📜 chalk-npm-3.0.0-e813208025-8e3ddf3981.zip
|  |  |  |- 📜 react-plotly.js-npm-2.6.0-7599bbc0ed-e826a3c94e.zip
|  |  |  |- 📜 unbox-primitive-npm-1.0.2-cb56a05066-b7a1cf5862.zip
|  |  |  |- 📜 socket.io-client-npm-4.6.1-fbfbf6a1e5-cc6abd3f9d.zip
|  |  |  |- 📜 plotly.js-npm-2.20.0-7411778dc6-7c0555247b.zip
|  |  |  |- 📜 quickselect-npm-2.0.0-620eb59fdc-ed2e784310.zip
|  |  |  |- 📜 memoize-one-npm-6.0.0-8b2a2cd020-f185ea69f7.zip
|  |  |  |- 📜 d3-array-npm-1.2.4-37b8938a64-d0be1fa7d7.zip
|  |  |  |- 📜 babel-plugin-styled-components-npm-2.0.7-543710bd48-80b06b10db.zip
|  |  |  |- 📜 glslify-deps-npm-1.3.2-16b5c1d761-3eb50a2617.zip
|  |  |  |- 📜 jsx-ast-utils-npm-3.3.3-3d3171e1e4-a2ed78cac4.zip
|  |  |  |- 📜 ignore-npm-5.2.4-fbe6e989e5-3d4c309c60.zip
|  |  |  |- 📜 supports-color-npm-5.5.0-183ac537bc-95f6f4ba5a.zip
|  |  |  |- 📜 point-in-polygon-npm-1.1.0-7a1fd13f23-67a6374f0b.zip
|  |  |  |- 📜 openai-npm-3.3.0-62dcac56ba-28ccff8c09.zip
|  |  |  |- 📜 style-mod-npm-4.0.2-5954d04da6-4bac8877e0.zip
|  |  |  |- 📜 xtend-npm-4.0.2-7f2375736e-ac5dfa738b.zip
|  |  |  |- 📜 @turf-bbox-npm-6.5.0-7e0db31887-537be56ae0.zip
|  |  |  |- 📜 @grpc-proto-loader-npm-0.6.13-658ac26dfb-863417e961.zip
|  |  |  |- 📜 parse-svg-path-npm-0.1.2-8bd0732a8f-bba7d4b420.zip
|  |  |  |- 📜 @types-d3-chord-npm-3.0.2-26d4b03a43-7ea3398d82.zip
|  |  |  |- 📜 d3-dispatch-npm-3.0.1-5f44c3166f-fdfd4a230f.zip
|  |  |  |- 📜 is-svg-path-npm-1.0.2-ac0df9ad01-ed35f610d1.zip
|  |  |  |- 📜 css-font-weight-keywords-npm-1.0.0-c93978e1a2-6a36eff4c8.zip
|  |  |  |- 📜 @types-d3-scale-npm-4.0.3-f929b25483-76684da851.zip
|  |  |  |- 📜 @turf-area-npm-6.5.0-8edd2bbf40-4b62c6874f.zip
|  |  |  |- 📜 css-font-style-keywords-npm-1.0.1-a78c79bca9-136720ebf5.zip
|  |  |  |- 📜 ms-npm-2.1.2-ec0c1512ff-673cdb2c31.zip
|  |  |  |- 📜 color-alpha-npm-1.0.4-4bc1d2b727-e0e5dd4c7b.zip
|  |  |  |- 📜 map-limit-npm-0.0.1-4a3dc66657-e7ad9a6603.zip
|  |  |  |- 📜 to-fast-properties-npm-2.0.0-0dc60cc481-be2de62fe5.zip
|  |  |  |- 📜 @firebase-remote-config-compat-npm-0.2.4-8b6e955c61-c3e6767fbd.zip
|  |  |  |- 📜 postcss-value-parser-npm-4.2.0-3cef602a6a-819ffab0c9.zip
|  |  |  |- 📜 object.fromentries-npm-2.0.6-424cf4cd3c-453c6d6941.zip
|  |  |  |- 📜 @types-istanbul-lib-coverage-npm-2.0.4-734954bb56-a25d7589ee.zip
|  |  |  |- 📜 @types-geojson-npm-7946.0.10-deca8d1263-12c407c2dc.zip
|  |  |  |- 📜 its-fine-npm-1.1.0-88a9e0e05f-4b8cf42b43.zip
|  |  |  |- 📜 regexp.prototype.flags-npm-1.4.3-df1c08b65d-51228bae73.zip
|  |  |  |- 📜 topojson-client-npm-3.1.0-70e59c7f28-8c029a4f18.zip
|  |  |  |- 📜 validate.io-number-npm-1.0.3-03b6276c54-42418aeb6c.zip
|  |  |  |- 📜 redux-mock-store-npm-1.5.4-87bd452380-571eab2cca.zip
|  |  |  |- 📜 ms-npm-2.0.0-9e1101a471-0e6a22b8b7.zip
|  |  |  |- 📜 @firebase-installations-types-npm-0.5.0-4a3d231f67-6d8449a6d1.zip
|  |  |  |- 📜 firebase-npm-9.18.0-02b1ba5566-ead7cf2771.zip
|  |  |  |- 📜 @emotion-serialize-npm-1.1.1-b082a29d71-24cfd5b16e.zip
|  |  |  |- 📜 @firebase-performance-npm-0.6.4-3f340cd5de-3e9829c473.zip
|  |  |  |- 📜 @types-lodash-npm-4.14.194-f099c0742e-113f34831c.zip
|  |  |  |- 📜 @dnd-kit-utilities-npm-3.2.1-e4b7ea044f-038fd5cc13.zip
|  |  |  |- 📜 gud-npm-1.0.0-9747ac46ec-3e2eb37cf7.zip
|  |  |  |- 📜 array-range-npm-1.0.1-76cf00208c-ca00a9773b.zip
|  |  |  |- 📜 @jest-schemas-npm-29.4.3-7d963e8d97-ac754e245c.zip
|  |  |  |- 📜 react-reconciler-npm-0.29.0-57f1460fdd-730db9cf45.zip
|  |  |  |- 📜 lodash-npm-4.17.21-6382451519-eb835a2e51.zip
|  |  |  |- 📜 object.values-npm-1.1.6-ab9b67ccd3-f6fff9fd81.zip
|  |  |  |- 📜 @babel-helper-string-parser-npm-7.22.5-448ff0e489-836851ca5e.zip
|  |  |  |- 📜 @types-unist-npm-2.0.6-82641b4aa5-25cb860ff1.zip
|  |  |  |- 📜 redux-npm-4.2.1-e7e2cf2e37-f63b9060c3.zip
|  |  |  |- 📜 @firebase-util-npm-1.9.3-f73af1bb9f-b2dbd39229.zip
|  |  |  |- 📜 pbf-npm-3.2.1-d33be8e429-8033f5e21f.zip
|  |  |  |- 📜 debug-npm-2.6.9-7d4cb597dc-d2f51589ca.zip
|  |  |  |- 📜 @hypnosphi-create-react-context-npm-0.3.1-01f6252b38-d2f069a562.zip
|  |  |  |- 📜 is-shared-array-buffer-npm-1.0.2-32e4181fcd-9508929cf1.zip
|  |  |  |- 📜 d3-format-npm-1.4.5-a17fc8af8f-1b8b2c0bca.zip
|  |  |  |- 📜 typescript-npm-5.0.2-66dd4bd4f0-bef1dcd166.zip
|  |  |  |- 📜 es6-symbol-npm-3.1.3-34d72f2a23-cd49722c2a.zip
|  |  |  |- 📜 watchpack-npm-2.4.0-7ec4b9cc65-23d4bc5863.zip
|  |  |  |- 📜 @types-react-plotly.js-npm-2.6.0-d14e27386a-91ab4eb8f1.zip
|  |  |  |- 📜 d3-timer-npm-1.0.10-af1ad28ff9-f704095367.zip
|  |  |  |- 📜 right-now-npm-1.0.0-cd931eff88-3969ddecef.zip
|  |  |  |- 📜 string-width-npm-4.2.3-2c27177bae-e52c10dc3f.zip
|  |  |  |- 📜 @types-scheduler-npm-0.16.2-ba3a7d8c68-b6b4dcfeae.zip
|  |  |  |- 📜 available-typed-arrays-npm-1.0.5-88f321e4d3-20eb47b3ce.zip
|  |  |  |- 📜 @babel-types-npm-7.23.0-332fd21daf-215fe04bd7.zip
|  |  |  |- 📜 levn-npm-0.4.1-d183b2d7bb-12c5021c85.zip
|  |  |  |- 📜 @babel-traverse-npm-7.21.3-b3b3d9c94e-0af5bcd47a.zip
|  |  |  |- 📜 jest-message-util-npm-29.5.0-910b21363f-daddece6bb.zip
|  |  |  |- 📜 @babel-helper-split-export-declaration-npm-7.18.6-53ebf8ad4c-c6d3dede53.zip
|  |  |  |- 📜 @swc-helpers-npm-0.5.2-f81ca286ad-51d7e3d8bd.zip
|  |  |  |- 📜 react-popper-npm-1.3.11-7eb852583d-a0f5994f57.zip
|  |  |  |- 📜 @grpc-proto-loader-npm-0.7.5-53f472433f-ca3a16fc18.zip
|  |  |  |- 📜 debug-npm-4.3.4-4513954577-3dbad3f94e.zip
|  |  |  |- 📜 is-mobile-npm-4.0.0-28382eb54e-1c4f32ab03.zip
|  |  |  |- 📜 glob-npm-7.2.3-2d866d17a5-29452e97b3.zip
|  |  |  |- 📜 flat-cache-npm-3.0.4-ee77e5911e-4fdd10ecbc.zip
|  |  |  |- 📜 es-abstract-npm-1.21.2-f4ebace1ab-037f55ee5e.zip
|  |  |  |- 📜 math-log2-npm-1.0.1-7a574a0dda-b9a9c746ec.zip
|  |  |  |- 📜 react-filerobot-image-editor-npm-4.3.8-eb296a2777-4e503723c1.zip
|  |  |  |- 📜 @firebase-database-npm-0.14.4-89bc84f6f2-cc2f520a6b.zip
|  |  |  |- 📜 @mui-system-npm-5.11.13-9eca9ab5d4-e6f1852ecf.zip
|  |  |  |- 📜 is-arguments-npm-1.1.1-eff4f6d4d7-7f02700ec2.zip
|  |  |  |- 📜 sax-npm-1.2.4-178f05f12f-d3df7d32b8.zip
|  |  |  |- 📜 @types-d3-npm-7.4.0-7025c582e3-d1383f5fca.zip
|  |  |  |- 📜 @codemirror-state-npm-6.2.0-19618854d2-fdc99c773d.zip
|  |  |  |- 📜 color-convert-npm-1.9.3-1fe690075e-fd7a64a17c.zip
|  |  |  |- 📜 react-lifecycles-compat-npm-3.0.4-d5e285a39e-a904b0fc0a.zip
|  |  |  |- 📜 function.prototype.name-npm-1.1.5-e776a642bb-acd21d733a.zip
|  |  |  |- 📜 @reactflow-core-npm-11.7.4-0705fb1a45-8e0bef41d6.zip
|  |  |  |- 📜 ansi-styles-npm-3.2.1-8cb8107983-d85ade01c1.zip
|  |  |  |- 📜 performance-now-npm-2.1.0-45e3ce7e49-534e641aa8.zip
|  |  |  |- 📜 @mui-base-npm-5.0.0-alpha.121-7d50bf1eb8-b14c9b5ed6.zip
|  |  |  |- 📜 static-eval-npm-2.1.0-d3c8eda113-21297ee9af.zip
|  |  |  |- 📜 has-bigints-npm-1.0.2-52732e614d-390e31e7be.zip
|  |  |  |- 📜 word-npm-0.3.0-da20365d4a-f84e706188.zip
|  |  |  |- 📜 combined-stream-npm-1.0.8-dc14d4a63a-49fa4aeb49.zip
|  |  |  |- 📜 @firebase-messaging-compat-npm-0.2.4-77dac8ba7b-60b0908da2.zip
|  |  |  |- 📜 @types-redux-mock-store-npm-1.0.3-0f91ea344f-b8c76be560.zip
|  |  |  |- 📜 dir-glob-npm-3.0.1-1aea628b1b-fa05e18324.zip
|  |  |  |- 📜 camelize-npm-1.0.1-d86ebe085a-91d8611d09.zip
|  |  |  |- 📜 bl-npm-2.2.1-f294e1ea12-4f5d9b2589.zip
|  |  |  |- 📜 @grpc-grpc-js-npm-1.7.3-367eafd856-cb05aae459.zip
|  |  |  |- 📜 globals-npm-13.20.0-4565a722e7-ad1ecf914b.zip
|  |  |  |- 📜 string.prototype.trimend-npm-1.0.6-304246ecc1-0fdc34645a.zip
|  |  |  |- 📜 file-entry-cache-npm-6.0.1-31965cf0af-f49701feaa.zip
|  |  |  |- 📜 dequal-npm-2.0.3-53a630c60e-8679b850e1.zip
|  |  |  |- 📜 color-alpha-npm-1.1.3-a1ffcfb62f-7c47fa16e1.zip
|  |  |  |- 📜 lodash.camelcase-npm-4.3.0-bf268e3bf0-cb9227612f.zip
|  |  |  |- 📜 @emotion-unitless-npm-0.7.5-14e1171640-f976e5345b.zip
|  |  |  |- 📜 yaml-npm-1.10.2-0e780aebdf-ce4ada136e.zip
|  |  |  |- 📜 dup-npm-1.0.0-1cfdf98dfa-1abda5b5b0.zip
|  |  |  |- 📜 @plotly-regl-npm-2.1.2-b3562d6a51-ea3364f799.zip
|  |  |  |- 📜 redux-thunk-npm-2.4.2-3acdaaf7b0-c7f757f6c3.zip
|  |  |  |- 📜 @protobufjs-fetch-npm-1.1.0-ca857b7df4-3fce7e09eb.zip
|  |  |  |- 📜 has-property-descriptors-npm-1.0.0-56289b918d-a6d3f0a266.zip
|  |  |  |- 📜 @floating-ui-core-npm-1.2.4-21f7249cea-1c163ea180.zip
|  |  |  |- 📜 path-type-npm-4.0.0-10d47fc86a-5b1e2daa24.zip
|  |  |  |- 📜 @jridgewell-resolve-uri-npm-3.1.0-6ff2351e61-b5ceaaf9a1.zip
|  |  |  |- 📜 optionator-npm-0.9.1-577e397aae-dbc6fa0656.zip
|  |  |  |- 📜 tslib-npm-1.14.1-102499115e-dbe628ef87.zip
|  |  |  |- 📜 @types-react-npm-18.0.28-c6157151cc-e752df9611.zip
|  |  |  |- 📜 @mui-icons-material-npm-5.11.16-d962649d08-db70426b6e.zip
|  |  |  |- 📜 fs.realpath-npm-1.0.0-c8f05d8126-99ddea01a7.zip
|  |  |  |- 📜 rw-npm-1.3.3-2197930a8d-c20d82421f.zip
|  |  |  |- 📜 min-indent-npm-1.0.1-77031f50e1-bfc6dd03c5.zip
|  |  |  |- 📜 css-system-font-keywords-npm-1.0.0-6120cb740e-2a2ce26d6f.zip
|  |  |  |- 📜 tr46-npm-0.0.3-de53018915-726321c5ea.zip
|  |  |  |- 📜 @typescript-eslint-visitor-keys-npm-5.58.0-06654486ba-ab2d1f3766.zip
|  |  |  |- 📜 color-space-npm-2.0.0-3fb0e00514-2abfa96412.zip
|  |  |  |- 📜 json5-npm-2.2.3-9962c55073-2a7436a933.zip
|  |  |  |- 📜 xtend-npm-2.2.0-eb3dffa78b-9fcd1ddabe.zip
|  |  |  |- 📜 deep-is-npm-0.1.4-88938b5a67-edb65dd0d7.zip
|  |  |  |- 📜 whatwg-url-npm-5.0.0-374fb45e60-b8daed4ad3.zip
|  |  |  |- 📜 json-schema-traverse-npm-0.4.1-4759091693-7486074d3b.zip
|  |  |  |- 📜 color-normalize-npm-1.5.2-e5925fe94e-162686b78d.zip
|  |  |  |- 📜 binary-search-bounds-npm-2.0.5-fa048fb646-e073e26557.zip
|  |  |  |- 📜 @eslint-js-npm-8.36.0-1f52b8accd-b7d6b84b82.zip
|  |  |  |- 📜 utils-copy-npm-1.1.1-67096439d8-c71b285cbe.zip
|  |  |  |- 📜 @types-warning-npm-3.0.0-aafa4d7846-120dcf9060.zip
|  |  |  |- 📜 supports-color-npm-7.2.0-606bfcf7da-3dda818de0.zip
|  |  |  |- 📜 is-finite-npm-1.1.0-c6324c0f8f-532b97ed3d.zip
|  |  |  |- 📜 @reactflow-background-npm-11.2.4-b112968d6e-17ca98de50.zip
|  |  |  |- 📜 @codemirror-search-npm-6.2.3-71ab7d96c5-7ab0ffab79.zip
|  |  |  |- 📜 strip-ansi-npm-6.0.1-caddc7cb40-f3cd25890a.zip
|  |  |  |- 📜 use-sync-external-store-npm-1.2.0-44f75d2564-5c639e0f8d.zip
|  |  |  |- 📜 inherits-npm-2.0.4-c66b3957a0-4a48a73384.zip
|  |  |  |- 📜 fast-levenshtein-npm-2.0.6-fcd74b8df5-92cfec0a8d.zip
|  |  |  |- 📜 escape-string-regexp-npm-4.0.0-4b531d8d59-98b48897d9.zip
|  |  |  |- 📜 strongly-connected-components-npm-1.0.1-8d63286c73-f731c4a1e9.zip
|  |  |  |- 📜 deep-equal-npm-2.2.0-d9712e0040-46a34509d2.zip
|  |  |  |- 📜 @types-d3-color-npm-3.1.0-e4a43fff88-b1856f17d6.zip
|  |  |  |- 📜 shebang-command-npm-2.0.0-eb2b01921d-6b52fe8727.zip
|  |  |  |- 📜 gestalt-datepicker-npm-101.3.9-41423eb763-b26aac7480.zip
|  |  |  |- 📜 format-npm-0.2.2-679f3acc64-646a60e133.zip
|  |  |  |- 📜 idb-npm-7.0.1-cc57c42817-6152678956.zip
|  |  |  |- 📜 convert-source-map-npm-1.9.0-e294555f4b-dc55a1f28d.zip
|  |  |  |- 📜 @turf-helpers-npm-6.5.0-a40ad42565-d57f746351.zip
|  |  |  |- 📜 uncontrollable-npm-8.0.0-96cef5cc40-d46a2e2911.zip
|  |  |  |- 📜 @mui-types-npm-7.2.3-36b2c98922-b8511cb78f.zip
|  |  |  |- 📜 @types-d3-geo-npm-3.0.3-f8d41ff06d-d2f0d38602.zip
|  |  |  |- 📜 @types-testing-library__jest-dom-npm-5.14.5-251c4c9d75-dcb0541675.zip
|  |  |  |- 📜 regl-error2d-npm-2.0.12-a8f745bdea-a7a2f22c05.zip
|  |  |  |- 📜 @emotion-stylis-npm-0.8.5-3e9db8959f-67ff595844.zip
|  |  |  |- 📜 ajv-npm-6.12.6-4b5105e2b2-874972efe5.zip
|  |  |  |- 📜 prelude-ls-npm-1.2.1-3e4d272a55-cd192ec0d0.zip
|  |  |  |- 📜 import-fresh-npm-3.3.0-3e34265ca9-2cacfad06e.zip
|  |  |  |- 📜 @types-lodash.camelcase-npm-4.3.7-24bf01b48e-ef068b921a.zip
|  |  |  |- 📜 string-split-by-npm-1.0.0-0ed3e2c32a-bd38cf3b3d.zip
|  |  |  |- 📜 defined-npm-1.0.1-7471d27847-b1a852300b.zip
|  |  |  |- 📜 to-px-npm-1.0.1-a66877c039-4cf87de444.zip
|  |  |  |- 📜 glsl-token-properties-npm-1.0.1-c5dfeda50c-9b4d1caf02.zip
|  |  |  |- 📜 pxls-npm-2.3.2-6c16de68e5-133be77f0d.zip
|  |  |  |- 📜 @nodelib-fs.walk-npm-1.2.8-b4a89da548-190c643f15.zip
|  |  |  |- 📜 hsluv-npm-0.0.3-7066bd484c-2cd6dbe342.zip
|  |  |  |- 📜 stream-shift-npm-1.0.1-9526210fa7-59b82b44b2.zip
|  |  |  |- 📜 optionator-npm-0.8.3-bc555bc5b7-b8695ddf3d.zip
|  |  |  |- 📜 is-weakmap-npm-2.0.1-88ca3d1dc4-1222bb7e90.zip
|  |  |  |- 📜 fast-deep-equal-npm-3.1.3-790edcfcf5-e21a9d8d84.zip
|  |  |  |- 📜 p-limit-npm-3.1.0-05d2ede37f-7c3690c4db.zip
|  |  |  |- 📜 @typescript-eslint-scope-manager-npm-5.58.0-a1ccd28e55-f0d3df5cc3.zip
|  |  |  |- 📜 d3-drag-npm-3.0.0-cf7b48417f-d297231e60.zip
|  |  |  |- 📜 @popperjs-core-npm-2.11.6-5bcdc104bd-47fb328cec.zip
|  |  |  |- 📜 glsl-tokenizer-npm-2.1.5-41724a73eb-daf70e91c6.zip
|  |  |  |- 📜 highlight.js-npm-10.7.3-247e67d5c0-defeafcd54.zip
|  |  |  |- 📜 color-convert-npm-2.0.1-79730e935b-79e6bdb9fd.zip
|  |  |  |- 📜 stream-parser-npm-0.3.1-0b70187c85-4d86ff8cff.zip
|  |  |  |- 📜 css-global-keywords-npm-1.0.1-cb92277c8f-390c46d9a0.zip
|  |  |  |- 📜 @jridgewell-trace-mapping-npm-0.3.17-57578fd48c-9d703b859c.zip
|  |  |  |- 📜 @babel-parser-npm-7.21.3-0ad17a2817-a71e6456a1.zip
|  |  |  |- 📜 ansi-regex-npm-5.0.1-c963a48615-2aa4bb54ca.zip
|  |  |  |- 📜 @typescript-eslint-eslint-plugin-npm-5.58.0-d549b94dee-e5d76d43c4.zip
|  |  |  |- 📜 @fortawesome-fontawesome-common-types-npm-6.4.2-1f8b184e1e-4a22932bd0.zip
|  |  |  |- 📜 mouse-event-offset-npm-3.0.2-ce79738a4e-f8cf9885bc.zip
|  |  |  |- 📜 type-npm-2.7.2-626963ea46-0f42379a8a.zip
|  |  |  |- 📜 earcut-npm-2.2.4-e823546b2f-aea0466cb2.zip
|  |  |  |- 📜 json-parse-even-better-errors-npm-2.3.1-144d62256e-798ed4cf33.zip
|  |  |  |- 📜 crypto-js-npm-4.1.1-38a3b8c19d-b3747c12ee.zip
|  |  |  |- 📜 concat-map-npm-0.0.1-85a921b7ee-902a9f5d89.zip
|  |  |  |- 📜 resolve-patch-be395eb267-fbdc248b89.zip
|  |  |  |- 📜 yargs-parser-npm-20.2.9-a1d19e598d-8bb69015f2.zip
|  |  |  |- 📜 levn-npm-0.3.0-48d774b1c2-0d084a5242.zip
|  |  |  |- 📜 validate.io-ndarray-like-npm-1.0.0-f50e5228ae-1dc014d81f.zip
|  |  |  |- 📜 is-number-npm-7.0.0-060086935c-456ac6f8e0.zip
|  |  |  |- 📜 @types-json-schema-npm-7.0.11-79462ae5ca-527bddfe62.zip
|  |  |  |- 📜 @types-d3-interpolate-npm-3.0.1-6fb3cc4131-29ce472968.zip
|  |  |  |- 📜 validate.io-matrix-like-npm-1.0.2-d31f61b84a-8ba77ddd34.zip
|  |  |  |- 📜 acorn-npm-8.8.2-9d518fd7d3-f790b99a1b.zip
|  |  |  |- 📜 @types-d3-path-npm-3.0.0-73db3fee36-af7f45ea91.zip
|  |  |  |- 📜 @babel-code-frame-npm-7.18.6-25229a7e34-195e2be317.zip
|  |  |  |- 📜 react-icons-npm-4.8.0-aa5423cd6c-4dbba7ad98.zip
|  |  |  |- 📜 @mui-styled-engine-npm-5.11.11-0e7d47c170-63b71aafe7.zip
|  |  |  |- 📜 @firebase-storage-npm-0.11.2-de1a26727b-0e54b8f783.zip
|  |  |  |- 📜 @restart-ui-npm-1.6.2-b84d838854-599c71cf1f.zip
|  |  |  |- 📜 @lezer-lr-npm-1.3.3-4ce9e8763b-1804074c79.zip
|  |  |  |- 📜 strip-indent-npm-3.0.0-519e75a28d-18f045d57d.zip
|  |  |  |- 📜 resolve-npm-2.0.0-next.4-3d0bd8621e-c438ac9a65.zip
|  |  |  |- 📜 color-space-npm-1.16.0-2ec67532ca-655ae748f8.zip
|  |  |  |- 📜 is-bigint-npm-1.0.4-31c2eecbc9-c56edfe09b.zip
|  |  |  |- 📜 element-size-npm-1.1.1-e47607ab44-0592332e84.zip
|  |  |  |- 📜 konva-npm-8.4.2-748f1bbf28-5be3d723ac.zip
|  |  |  |- 📜 react-is-npm-16.13.1-a9b9382b4f-f7a19ac349.zip
|  |  |  |- 📜 d3-geo-npm-1.12.1-fbb760bdb1-8ede498e5f.zip
|  |  |  |- 📜 resolve-npm-0.6.3-ffde2bd7ce-c3b5d34ba7.zip
|  |  |  |- 📜 readable-stream-npm-1.0.34-db63158f3f-85042c537e.zip
|  |  |  |- 📜 cookie-npm-0.3.1-111f39dba6-5309937344.zip
|  |  |  |- 📜 @babel-helper-validator-identifier-npm-7.22.20-18305bb306-136412784d.zip
|  |  |  |- 📜 once-npm-1.4.0-ccf03ef07a-cd0a885013.zip
|  |  |  |- 📜 which-npm-2.0.2-320ddf72f7-1a5c563d3c.zip
|  |  |  |- 📜 @choojs-findup-npm-0.2.1-13bdf9d041-9496321caa.zip
|  |  |  |- 📜 dom-helpers-npm-5.2.1-b38bb4470b-863ba9e086.zip
|  |  |  |- 📜 @types-d3-axis-npm-3.0.2-f72a156ed4-3067a94957.zip
|  |  |  |- 📜 @protobufjs-aspromise-npm-1.1.2-71d00b938f-011fe7ef08.zip
|  |  |  |- 📜 @types-d3-scale-chromatic-npm-3.0.0-807f96c8c9-e06afffd27.zip
|  |  |  |- 📜 @uiw-react-codemirror-npm-4.19.9-e9eddfe65b-ed0d9a7b92.zip
|  |  |  |- 📜 fault-npm-1.0.4-2788bc13e3-5ac610d8b0.zip
|  |  |  |- 📜 path-is-absolute-npm-1.0.1-31bc695ffd-060840f92c.zip
|  |  |  |- 📜 @firebase-app-compat-npm-0.2.5-ed1acd410c-e8a84e8a5e.zip
|  |  |  |- 📜 reselect-npm-4.1.7-c37108c640-738d8e2b8f.zip
|  |  |  |- 📜 @jest-expect-utils-npm-29.5.0-69b6ba2629-c46fb677c8.zip
|  |  |  |- 📜 @next-env-npm-14.0.1-6399964ef4-1fab6732f8.zip
|  |  |  |- 📜 almost-equal-npm-1.1.0-48155ef50c-6022fbd07d.zip
|  |  |  |- 📜 @firebase-logger-npm-0.4.0-4e189c5236-4b5418f03a.zip
|  |  |  |- 📜 cliui-npm-7.0.4-d6b8a9edb6-ce2e8f578a.zip
|  |  |  |- 📜 validate.io-array-npm-1.0.6-d265c3d6a6-54eca83ebc.zip
|  |  |  |- 📜 esutils-npm-2.0.3-f865beafd5-22b5b08f74.zip
|  |  |  |- 📜 character-reference-invalid-npm-1.1.4-e5e17a1a38-20274574c7.zip
|  |  |  |- 📜 is-map-npm-2.0.2-486724dabc-ace3d0ecd6.zip
|  |  |  |- 📜 es-get-iterator-npm-1.1.3-7911befaac-8fa118da42.zip
|  |  |  |- 📜 tsutils-npm-3.21.0-347e6636c5-1843f4c1b2.zip
|  |  |  |- 📜 classcat-npm-5.0.4-57c2855a8a-77373c58fa.zip
|  |  |  |- 📜 pako-npm-1.0.11-b8f1b69d3e-1be2bfa1f8.zip
|  |  |  |- 📜 @types-react-dom-npm-18.0.11-27f8db2995-579691e4d5.zip
|  |  |  |- 📜 ts-jest-npm-29.0.5-30e5da5c24-f60f129c22.zip
|  |  |  |- 📜 validate.io-integer-npm-1.0.5-e0e50c7216-88b3f8bb5a.zip
|  |  |  |- 📜 @types-istanbul-lib-report-npm-3.0.0-50de3e6b3b-656398b62d.zip
|  |  |  |- 📜 regenerator-runtime-npm-0.13.11-90bf536060-27481628d2.zip
|  |  |  |- 📜 frac-npm-1.1.2-7e88efac4e-fbfbb28003.zip
|  |  |  |- 📜 @reactflow-controls-npm-11.1.15-2e5b04e065-7568c69bfa.zip
|  |  |  |- 📜 css-font-npm-1.2.0-dbdda0018d-e1b327c846.zip
|  |  |  |- 📜 get-intrinsic-npm-1.2.0-eb08ea9b1d-78fc0487b7.zip
|  |  |  |- 📜 resolve-patch-34cda421ec-4bf9f4f8a4.zip
|  |  |  |- 📜 delayed-stream-npm-1.0.0-c5a4c4cc02-46fe6e83e2.zip
|  |  |  |- 📜 glob-parent-npm-6.0.2-2cbef12738-c13ee97978.zip
|  |  |  |- 📜 fast-json-stable-stringify-npm-2.1.0-02e8905fda-b191531e36.zip
|  |  |  |- 📜 protobufjs-npm-6.11.4-af11968b80-b2fc6a0189.zip
|  |  |  |- 📜 @codemirror-commands-npm-6.2.2-6c0e7a80a9-d3aa1ca8cb.zip
|  |  |  |- 📜 es5-ext-npm-0.10.62-f20aca46cb-25f42f6068.zip
|  |  |  |- 📜 array.prototype.tosorted-npm-1.1.1-1be94ad4a7-7923324a67.zip
|  |  |  |- 📜 esrecurse-npm-4.3.0-10b86a887a-ebc17b1a33.zip
|  |  |  |- 📜 source-map-npm-0.6.1-1a3621db16-59ce8640cf.zip
|  |  |  |- 📜 css-to-react-native-npm-3.2.0-46e31a25e3-263be65e80.zip
|  |  |  |- 📜 mumath-npm-3.3.4-1d46407e79-1c4e9fbfa6.zip
|  |  |  |- 📜 @mui-x-data-grid-npm-6.0.4-de1d108409-8f84071287.zip
|  |  |  |- 📜 array-rearrange-npm-2.2.2-61c9dd2a22-bcf44e81b2.zip
|  |  |  |- 📜 fast-isnumeric-npm-1.1.4-a6a6ca91e1-7485fd8d9b.zip
|  |  |  |- 📜 @firebase-storage-types-npm-0.8.0-d8ce016559-05cf05be73.zip
|  |  |  |- 📜 property-information-npm-5.6.0-1322d29e0f-fcf87c6542.zip
|  |  |  |- 📜 array-normalize-npm-1.1.4-9b014481d2-821eda0e8a.zip
|  |  |  |- 📜 @codemirror-view-npm-6.9.2-1471a2d970-e6faaf1b2d.zip
|  |  |  |- 📜 refractor-npm-3.6.0-63276910f9-39b01c4168.zip
|  |  |  |- 📜 d3-ease-npm-3.0.1-f8f3709dc7-06e2ee5326.zip
|  |  |  |- 📜 @types-react-reconciler-npm-0.28.2-694fc46c5c-9720f76a33.zip
|  |  |  |- 📜 styled-jsx-npm-5.1.1-2557a209ba-523a33b386.zip
|  |  |  |- 📜 loose-envify-npm-1.4.0-6307b72ccf-6517e24e0c.zip
|  |  |  |- 📜 axios-npm-0.27.2-dbe3a48aea-38cb754046.zip
|  |  |  |- 📜 which-typed-array-npm-1.1.9-9559c95dfc-fe0178ca44.zip
|  |  |  |- 📜 canvas-fit-npm-1.5.0-5184f55bcb-5ac1eca0b4.zip
|  |  |  |- 📜 bs-logger-npm-0.2.6-7670f88b66-d34bdaf68c.zip
|  |  |  |- 📜 react-konva-npm-18.2.4-51a1623011-b741a877dd.zip
|  |  |  |- 📜 tinycolor2-npm-1.6.0-8df41252c6-6df4d07fce.zip
|  |  |  |- 📜 @types-d3-time-format-npm-4.0.0-ebddbc2ecb-ac3a841b0c.zip
|  |  |  |- 📜 prismjs-npm-1.27.0-ca4e1667c6-85c7f4a3e9.zip
|  |  |  |- 📜 react-transition-group-npm-4.4.5-98ea4ef96e-7560284010.zip
|  |  |  |- 📜 gl-matrix-npm-3.4.3-f2e6349faa-c47830ba72.zip
|  |  |  |- 📜 yargs-npm-16.2.0-547873d425-b14afbb51e.zip
|  |  |  |- 📜 chalk-npm-4.1.2-ba8b67ab80-fe75c9d5c7.zip
|  |  |  |- 📜 @babel-runtime-npm-7.21.0-c4ef698c89-7b33e25bfa.zip
|  |  |  |- 📜 space-separated-tokens-npm-1.1.5-2352c83473-8ef68f1cfa.zip
|  |  |  |- 📜 geojson-vt-npm-3.2.1-80c8f60496-7c7973cfaf.zip
|  |  |  |- 📜 prop-types-extra-npm-1.1.1-ebbe8d351d-ebf1c04868.zip
|  |  |  |- 📜 source-map-js-npm-1.0.2-ee4f9f9b30-c049a7fc4d.zip
|  |  |  |- 📜 is-number-object-npm-1.0.7-539d0e274d-d1e8d01bb0.zip
|  |  |  |- 📜 uri-js-npm-4.4.1-66d11cbcaf-7167432de6.zip
|  |  |  |- 📜 d3-selection-npm-3.0.0-39a42b4ca9-f4e60e1333.zip
|  |  |  |- 📜 @firebase-performance-compat-npm-0.2.4-714d2169ac-f44a6833f3.zip
|  |  |  |- 📜 @babel-helper-validator-identifier-npm-7.19.1-d84f19e1dc-0eca5e86a7.zip
|  |  |  |- 📜 image-palette-npm-2.1.0-903838f896-53bc499ddb.zip
|  |  |  |- 📜 @types-styled-components-npm-5.1.26-aabda06611-84f53b3101.zip
|  |  |  |- 📜 lie-npm-3.3.0-35ddd11a4d-33102302cf.zip
|  |  |  |- 📜 through2-npm-2.0.5-77d90f13cd-beb0f338aa.zip
|  |  |  |- 📜 @mui-private-theming-npm-5.11.13-3d71420ae2-9e5e02c648.zip
|  |  |  |- 📜 diff-sequences-npm-29.4.3-ffe403944f-28b265e04f.zip
|  |  |  |- 📜 hoist-non-react-statics-npm-3.3.2-e7b709e6c1-b153827042.zip
|  |  |  |- 📜 color-parse-npm-1.4.2-bd4a4dff72-3ed5916f87.zip
|  |  |  |- 📜 pretty-bytes-npm-6.1.0-fec0b4ea5a-cca3be45a2.zip
|  |  |  |- 📜 mouse-wheel-npm-1.2.0-fabd7810ef-28e41ccac4.zip
|  |  |  |- 📜 client-only-npm-0.0.1-07d3e9505c-0c16bf660d.zip
|  |  |  |- 📜 country-regex-npm-1.1.0-4434de3ad2-e9be62b811.zip
|  |  |  |- 📜 deep-equal-npm-1.1.1-67ff9c29b9-f92686f2c5.zip
|  |  |  |- 📜 emoji-regex-npm-8.0.0-213764015c-d4c5c39d5a.zip
|  |  |  |- 📜 clsx-npm-1.2.1-77792dc182-30befca801.zip
|  |  |  |- 📜 @babel-generator-npm-7.21.3-176ee60a78-be6bb5a32a.zip
|  |  |  |- 📜 @types-plotly.js-npm-2.12.18-6c2d2477ed-826176a469.zip
|  |  |  |- 📜 immer-npm-9.0.19-96ee7d3dab-f02ee53989.zip
|  |  |  |- 📜 is-hexadecimal-npm-1.0.4-b4091da09e-a452e04758.zip
|  |  |  |- 📜 @scaleflex-icons-npm-1.0.0-beta.99-21fda306cf-fd8603c279.zip
|  |  |  |- 📜 scheduler-npm-0.23.0-a379a6bc3b-d79192eeaa.zip
|  |  |  |- 📜 mapbox-gl-npm-1.10.1-3ea34c87e3-94e285367f.zip
|  |  |  |- 📜 is-string-blank-npm-1.0.1-81438a9c9f-00a0955c2b.zip
|  |  |  |- 📜 d3-time-format-npm-2.3.0-df09741a0b-5445eaaf2b.zip
|  |  |  |- 📜 invariant-npm-2.2.4-717fbdb119-cc3182d793.zip
|  |  |  |- 📜 grid-index-npm-1.1.0-fe69e26b3f-0e9d427b60.zip
|  |  |  |- 📜 has-flag-npm-4.0.0-32af9f0536-261a135703.zip
|  |  |  |- 📜 glsl-token-scope-npm-1.1.2-e6c5871b08-d62812c81a.zip
|  |  |  |- 📜 expect-npm-29.5.0-395e2d6fda-58f70b3869.zip
|  |  |  |- 📜 @types-react-syntax-highlighter-npm-15.5.6-cf4b144490-81a9f26da4.zip
|  |  |  |- 📜 lowlight-npm-1.20.0-771a13490e-14a1815d6b.zip
|  |  |  |- 📜 abs-svg-path-npm-0.1.1-e563d22137-af1a167c09.zip
|  |  |  |- 📜 util-deprecate-npm-1.0.2-e3fe1a219c-474acf1146.zip
|  |  |  |- 📜 @plotly-d3-sankey-npm-0.7.2-479774ee94-fc3f764c62.zip
|  |  |  |- 📜 utils-indexof-npm-1.0.0-409635751e-4f848f54ca.zip
|  |  |  |- 📜 @types-d3-polygon-npm-3.0.0-7fae120e00-2b4fbd864e.zip
|  |  |  |- 📜 glsl-token-whitespace-trim-npm-1.0.0-008d1fd6e6-ffb0d09118.zip
|  |  |  |- 📜 concat-stream-npm-1.6.2-2bee337060-1ef77032cb.zip
|  |  |  |- 📜 native-promise-only-npm-0.8.1-fb8355ffa6-bb4d8416c4.zip
|  |  |  |- 📜 d3-geo-projection-npm-2.9.0-826dff1fbb-05ff12195f.zip
|  |  |  |- 📜 path-parse-npm-1.0.7-09564527b7-49abf3d811.zip
|  |  |  |- 📜 braces-npm-3.0.2-782240b28a-e2a8e769a8.zip
|  |  |  |- 📜 indent-string-npm-4.0.0-7b717435b2-824cfb9929.zip
|  |  |  |- 📜 color-normalize-npm-1.5.0-5a2f197d5b-4217dada6e.zip
|  |  |  |- 📜 next-npm-14.0.1-1b487ba547-d142407f47.zip
|  |  |  |- 📜 crc-32-npm-1.2.2-28bdc12bcc-ad2d0ad0cb.zip
|  |  |  |- 📜 parse-json-npm-5.2.0-00a63b1199-62085b17d6.zip
|  |  |  |- 📜 is-path-inside-npm-3.0.3-2ea0ef44fd-abd50f0618.zip
|  |  |  |- 📜 to-regex-range-npm-5.0.1-f1e8263b00-f76fa01b3d.zip
|  |  |  |- 📜 cosmiconfig-npm-7.1.0-13a5090bcd-c53bf7befc.zip
|  |  |  |- 📜 @firebase-auth-types-npm-0.12.0-59c1335559-d7eeef6ece.zip
|  |  |  |- 📜 @types-d3-selection-npm-3.0.5-230949f5ef-77ea35c922.zip
|  |  |  |- 📜 atob-lite-npm-2.0.0-62802899eb-336880fdca.zip
|  |  |  |- 📜 focus-lock-npm-0.11.6-fb9117f534-6a407c4c45.zip
|  |  |  |- 📜 @plotly-d3-npm-3.8.1-7a99dd05ef-917e686b7c.zip
|  |  |  |- 📜 css-font-size-keywords-npm-1.0.0-9285f5ff7c-1b7479e850.zip
|  |  |  |- 📜 is-date-object-npm-1.0.5-88f3d08b5e-baa9077cdf.zip
|  |  |  |- 📜 picocolors-npm-1.0.0-d81e0b1927-a2e8092dd8.zip
|  |  |  |- 📜 yargs-parser-npm-21.1.1-8fdc003314-ed2d96a616.zip
|  |  |  |- 📜 path-exists-npm-4.0.0-e9e4f63eb0-505807199d.zip
|  |  |  |- 📜 follow-redirects-npm-1.15.2-1ec1dd82be-faa66059b6.zip
|  |  |  |- 📜 styled-components-npm-5.3.9-4d660d9c99-404311cc70.zip
|  |  |  |- 📜 to-uint8-npm-1.4.1-daf98bfa4b-ea9b6a18db.zip
|  |  |  |- 📜 safe-buffer-npm-5.2.1-3481c8aa9b-b99c4b41fd.zip
|  |  |  |- 📜 next-tick-npm-1.1.0-e0eb60d6a4-83b5cf3602.zip
|  |  |  |- 📜 @mui-core-downloads-tracker-npm-5.11.13-3e3f0594dc-b8a32c9fc4.zip
|  |  |  |- 📜 @types-parse-json-npm-4.0.0-298522afa6-fd6bce2b67.zip
|  |  |  |- 📜 safe-buffer-npm-5.1.2-c27fedf6c4-f2f1f7943c.zip
|  |  |  |- 📜 @sinclair-typebox-npm-0.25.24-d04d0f45ef-10219c58f4.zip
|  |  |  |- 📜 @types-crypto-js-npm-4.1.1-1c4ce3312a-ea3d6a67b6.zip
|  |  |  |- 📜 xmlhttprequest-ssl-npm-2.0.0-a9c0d5efed-1e98df67f0.zip
|  |  |  |- 📜 prop-types-npm-15.8.1-17c71ee7ee-c056d3f1c0.zip
|  |  |  |- 📜 node-fetch-npm-2.6.7-777aa2a6df-8d816ffd1e.zip
|  |  |  |- 📜 fast-glob-npm-3.2.12-162763bbae-0b1990f6ce.zip
|  |  |  |- 📜 @types-node-npm-18.15.3-d092b0c75c-31b1d92475.zip
|  |  |  |- 📜 yallist-npm-4.0.0-b493d9e907-343617202a.zip
|  |  |  |- 📜 escape-string-regexp-npm-2.0.0-aef69d2a25-9f8a2d5743.zip
|  |  |  |- 📜 is-boolean-object-npm-1.1.2-ecbd575e6a-c03b23dbaa.zip
|  |  |  |- 📜 @firebase-database-compat-npm-0.3.4-7afd930d14-d5162718f0.zip
|  |  |  |- 📜 string_decoder-npm-1.1.1-e46a6c1353-9ab7e56f9d.zip
|  |  |  |- 📜 resolve-patch-0c52e0e4f7-5656f4d0be.zip
|  |  |  |- 📜 d3-quadtree-npm-1.0.7-131ab23658-32181f578c.zip
|  |  |  |- 📜 @firebase-analytics-npm-0.9.4-fa18fa365f-0a131d60b5.zip
|  |  |  |- 📜 @mapbox-mapbox-gl-supported-npm-1.5.0-1a6e7562c1-0861f89e2a.zip
|  |  |  |- 📜 text-table-npm-0.2.0-d92a778b59-b6937a38c8.zip
|  |  |  |- 📜 @firebase-functions-types-npm-0.6.0-d17de45b5d-00a2a6db2a.zip
|  |  |  |- 📜 react-syntax-highlighter-npm-15.5.0-da5363373b-c082b48f30.zip
|  |  |  |- 📜 color-name-npm-1.1.3-728b7b5d39-09c5d3e33d.zip
|  |  |  |- 📜 minimist-npm-1.2.8-d7af7b1dce-75a6d645fb.zip
|  |  |  |- 📜 world-calendars-npm-1.0.3-5ebbc0630c-bf3470042a.zip
|  |  |  |- 📜 @codemirror-language-npm-6.6.0-43696d4b79-bb9411620e.zip
|  |  |  |- 📜 @types-yargs-npm-17.0.22-35cdb1bdeb-0773523fda.zip
|  |  |  |- 📜 @scaleflex-icons-npm-1.0.0-45e2223b73-98e795a268.zip
|  |  |  |- 📜 @scaleflex-ui-npm-1.0.0-beta.99-83f2a93a82-804a46772b.zip
|  |  |  |- 📜 regl-splom-npm-1.0.14-a856cb79df-6ba15b3871.zip
|  |  |  |- 📜 has-tostringtag-npm-1.0.0-b1fcf3ab55-cc12eb28cb.zip
|  |  |  |- 📜 is-extglob-npm-2.1.1-0870ea68b5-df033653d0.zip
|  |  |  |- 📜 codemirror-npm-6.0.1-a317bb67bb-1a78f7077a.zip
|  |  |  |- 📜 @babel-types-npm-7.21.3-2a27aede05-b750274718.zip
|  |  |  |- 📜 @firebase-storage-compat-npm-0.3.2-4397e528be-47d0b71b8c.zip
|  |  |  |- 📜 @firebase-installations-npm-0.6.4-72227b0fe4-e36cbca01b.zip
|  |  |  |- 📜 @swc-helpers-npm-0.4.14-f806c3fb16-273fd3f3fc.zip
|  |  |  |- 📜 escalade-npm-3.1.1-e02da076aa-a3e2a99f07.zip
|  |  |  |- 📜 get-caller-file-npm-2.0.5-80e8a86305-b9769a836d.zip
|  |  |  |- 📜 quantize-npm-1.0.2-0828a339bc-8f224e75f6.zip
|  |  |  |- 📜 color-rgba-npm-2.1.1-30322a67c9-0bdceaffa2.zip
|  |  |  |- 📜 object-is-npm-1.1.5-48a862602b-989b18c4cb.zip
|  |  |  |- 📜 define-properties-npm-1.2.0-3547cd0fd2-e60aee6a19.zip
|  |  |  |- 📜 @jridgewell-sourcemap-codec-npm-1.4.14-f5f0630788-61100637b6.zip
|  |  |  |- 📜 glob-parent-npm-5.1.2-021ab32634-f4f2bfe242.zip
|  |  |  |- 📜 semver-npm-7.5.4-c4ad957fcd-12d8ad952f.zip
|  |  |  |- 📜 is-weakset-npm-2.0.2-b3cbc6c9cd-5d8698d1fa.zip
|  |  |  |- 📜 array-union-npm-2.1.0-4e4852b221-5bee12395c.zip
|  |  |  |- 📜 esprima-npm-4.0.1-1084e98778-b45bc805a6.zip
|  |  |  |- 📜 use-isomorphic-layout-effect-npm-1.1.2-65facd0a4b-a6532f7fc9.zip
|  |  |  |- 📜 eslint-plugin-react-npm-7.32.2-b8b92d1b99-2232b3b894.zip
|  |  |  |- 📜 aria-query-npm-5.1.3-9632eccdee-929ff95f02.zip
|  |  |  |- 📜 is-negative-zero-npm-2.0.2-0adac91f15-f3232194c4.zip
|  |  |  |- 📜 caniuse-lite-npm-1.0.30001474-a9fd6e4aa5-c05faab958.zip
|  |  |  |- 📜 babel-plugin-syntax-jsx-npm-6.18.0-fcf0a98a71-0c7ce5b81d.zip
|  |  |  |- 📜 es-shim-unscopables-npm-1.0.0-06186593f1-83e95cadbb.zip
|  |  |  |- 📜 @lezer-highlight-npm-1.1.3-2be2a7b35a-90ec143ce4.zip
|  |  |  |- 📜 pretty-format-npm-27.5.1-cd7d49696f-cf610cffcb.zip
|  |  |  |- 📜 stack-trace-npm-0.0.9-5628ec44f6-5b1ff9708e.zip
|  |  |  |- 📜 isarray-npm-1.0.0-db4f547720-f032df8e02.zip
|  |  |  |- 📜 glsl-token-depth-npm-1.1.2-2c8fa14257-97fff701ee.zip
|  |  |  |- 📜 http-parser-js-npm-0.5.8-f80208ea99-6bbdf24298.zip
|  |  |  |- 📜 compute-dims-npm-1.1.0-f84a239915-c0141eceba.zip
|  |  |  |- 📜 react-is-npm-17.0.2-091bbb8db6-9d6d111d89.zip
|  |  |  |- 📜 prop-types-npm-15.7.2-d7a04f2274-5eef82fdda.zip
|  |  |  |- 📜 ws-npm-8.11.0-ab72116a01-316b33aba3.zip
|  |  |  |- 📜 escodegen-npm-1.14.3-a4dedc6eeb-381cdc4767.zip
|  |  |  |- 📜 glsl-token-descope-npm-1.0.2-658390c61c-a0d578d5e7.zip
|  |  |  |- 📜 es6-iterator-npm-2.0.3-4dadb0ccc1-6e48b1c2d9.zip
|  |  |  |- 📜 @reactflow-minimap-npm-11.5.4-31f6c1f671-01373f6345.zip
|  |  |  |- 📜 webgl-context-npm-2.2.0-c20a635d5e-b9ee376f86.zip
|  |  |  |- 📜 stop-iteration-iterator-npm-1.0.0-ea451e1609-d04173690b.zip
|  |  |  |- 📜 run-parallel-npm-1.2.0-3f47ff2034-cb4f97ad25.zip
|  |  |  |- 📜 @firebase-installations-compat-npm-0.2.4-602e0f12fc-a5774cf074.zip
|  |  |  |- 📜 internal-slot-npm-1.0.5-a2241f3e66-97e84046bf.zip
|  |  |  |- 📜 has-hover-npm-1.0.1-9df69d1e8b-ba5b89fa61.zip
|  |  |  |- 📜 function-bind-npm-1.1.1-b56b322ae9-b32fbaebb3.zip
|  |  |  |- 📜 espree-npm-9.5.0-ec4786604f-a7f110aefb.zip
|  |  |  |- 📜 find-up-npm-5.0.0-e03e9b796d-07955e3573.zip
|  |  |  |- 📜 react-toastify-npm-9.1.1-114b39ed7d-2039255539.zip
|  |  |  |- 📜 string-to-arraybuffer-npm-1.0.2-3d27ff83c3-4a04ee521a.zip
|  |  |  |- 📜 p-locate-npm-5.0.0-92cc7c7a3e-1623088f36.zip
|  |  |  |- 📜 polished-npm-3.7.2-ab1a513201-2f6172fef7.zip
|  |  |  |- 📜 mime-db-npm-1.52.0-b5371d6fd2-0d99a03585.zip
|  |  |  |- 📜 @emotion-hash-npm-0.9.0-efbc0b3f3f-b63428f7c8.zip
|  |  |  |- 📜 gl-text-npm-1.3.1-2a29640600-fb78872ba0.zip
|  |  |  |- 📜 @babel-helper-hoist-variables-npm-7.18.6-6eb061f405-fd9c35bb43.zip
|  |  |  |- 📜 lines-and-columns-npm-1.2.4-d6c7cc5799-0c37f9f7fa.zip
|  |  |  |- 📜 has-symbols-npm-1.0.3-1986bff2c4-a054c40c63.zip
|  |  |  |- 📜 polybooljs-npm-1.2.0-43e6b13741-a5faaa71c3.zip
|  |  |  |- 📜 long-npm-4.0.0-ecd96a31ed-16afbe8f74.zip
|  |  |  |- 📜 has-proto-npm-1.0.1-631ea9d820-febc5b5b53.zip
|  |  |  |- 📜 @socket.io-component-emitter-npm-3.1.0-3f778351c2-db069d9542.zip
|  |  |  |- 📜 buffer-from-npm-1.1.2-03d2f20d7e-0448524a56.zip
|  |  |  |- 📜 queue-microtask-npm-1.2.3-fcc98e4e2d-b676f8c040.zip
|  |  |  |- 📜 adler-32-npm-1.3.1-8493d3a628-c7f6b02df6.zip
|  |  |  |- 📜 path-key-npm-3.1.1-0e66ea8321-55cd7a9dd4.zip
|  |  |  |- 📜 react-google-recaptcha-npm-2.1.0-90708b8ebd-f4f4d248eb.zip
|  |  |  |- 📜 punycode-npm-2.3.0-df4bdce06b-39f760e09a.zip
|  |  |  |- 📜 gestalt-design-tokens-npm-101.1.10-c08240904c-a5d6496a1e.zip
|  |  |  |- 📜 array-find-index-npm-1.0.2-a7d5fbff35-aac128bf36.zip
|  |  |  |- 📜 find-root-npm-1.1.0-a16a94005f-b2a59fe4b6.zip
|  |  |  |- 📜 long-npm-5.2.1-3a12730171-9264da12d1.zip
|  |  |  |- 📜 source-map-npm-0.5.7-7c3f035429-5dc2043b93.zip
|  |  |  |- 📜 es-set-tostringtag-npm-2.0.1-c87b5de872-ec416a1294.zip
|  |  |  |- 📜 @firebase-app-npm-0.9.5-e662c6f847-cbe691158c.zip
|  |  |  |- 📜 for-each-npm-0.3.3-0010ca8cdd-6c48ff2bc6.zip
|  |  |  |- 📜 @protobufjs-utf8-npm-1.1.0-02c590807c-f9bf3163d1.zip
|  |  |  |- 📜 @firebase-database-types-npm-0.10.4-e1f4429410-4fcecd2122.zip
|  |  |  |- 📜 @firebase-analytics-types-npm-0.8.0-cd2e645f88-fe8647ccf2.zip
|  |  |  |- 📜 array-bounds-npm-1.0.1-03d2d55971-67367cfcaa.zip
|  |  |  |- 📜 character-entities-legacy-npm-1.1.4-e3e7c8ee55-fe03a82c15.zip
|  |  |  |- 📜 @humanwhocodes-config-array-npm-0.11.8-7955bfecc2-0fd6b3c54f.zip
|  |  |  |- 📜 utils-regex-from-string-npm-1.0.0-4d4a96e6c0-317444c904.zip
|  |  |  |- 📜 regex-regex-npm-1.0.0-45614d5025-68cfadb5f6.zip
|  |  |  |- 📜 @types-jest-npm-29.5.0-18eef6c3cc-cd877e5c56.zip
|  |  |  |- 📜 @restart-hooks-npm-0.4.9-09e7290a74-2481b21ee9.zip
|  |  |  |- 📜 @types-d3-random-npm-3.0.1-ba520ed342-7ed9f83ee3.zip
|  |  |  |- 📜 @firebase-analytics-compat-npm-0.2.4-167bb779fc-1f99fa716e.zip
|  |  |  |- 📜 supports-preserve-symlinks-flag-npm-1.0.0-f17c4d0028-53b1e247e6.zip
|  |  |  |- 📜 @types-d3-ease-npm-3.0.0-b342ad1e9f-1be7c99364.zip
|  |  |  |- 📜 @jest-types-npm-29.5.0-36a4c63efc-1811f94b19.zip
|  |  |  |- 📜 bitmap-sdf-npm-1.0.4-d4652f6dca-3165504a2a.zip
|  |  |  |- 📜 get-canvas-context-npm-1.0.2-169b8b9921-7068d49731.zip
|  |  |  |- 📜 string.prototype.trimstart-npm-1.0.6-0926caea6c-89080feef4.zip
|  |  |  |- 📜 d3-color-npm-3.1.0-fc73fe3b15-4931fbfda5.zip
|  |  |  |- 📜 const-pinf-float64-npm-1.0.0-fe2968657a-fb8f89f6ff.zip
|  |  |  |- 📜 through2-npm-0.6.5-562fbaa3f1-dfea228e31.zip
|  |  |  |- 📜 escape-string-regexp-npm-1.0.5-3284de402f-6092fda75c.zip
|  |  |  |- 📜 color-name-npm-1.1.4-025792b0ea-b044585952.zip
|  |  |  |- 📜 csstype-npm-3.1.1-3857baf48b-1f7b4f5fdd.zip
|  |  |  |- 📜 natural-compare-npm-1.4.0-97b75b362d-23ad088b08.zip
|  |  |  |- 📜 parenthesis-npm-3.1.8-3ab5e02936-47d86bb7d9.zip
|  |  |  |- 📜 @testing-library-react-npm-14.0.0-84fecd033b-4a54c8f56c.zip
|  |  |  |- 📜 websocket-extensions-npm-0.1.4-be839a9e56-5976835e68.zip
|  |  |  |- 📜 @mapbox-geojson-rewind-npm-0.5.2-716dd1ae97-721470ab5e.zip
|  |  |  |- 📜 nanoid-npm-3.3.6-e6d6ae7e71-7d0eda6570.zip
|  |  |  |- 📜 xlsx-npm-0.18.5-f70d417ac6-c5774d3c6a.zip
|  |  |  |- 📜 to-array-buffer-npm-3.2.0-8a5950de57-9f1051d198.zip
|  |  |  |- 📜 tinyqueue-npm-2.0.3-ceed389145-0b6bda46b6.zip
|  |  |  |- 📜 is-buffer-npm-2.0.5-17e563f277-764c9ad8b5.zip
|  |  |  |- 📜 @react-aria-ssr-npm-3.5.0-a1e5c3dc4a-3287fe756f.zip
|  |  |  |- 📜 detect-node-es-npm-1.1.0-2ad57e0b50-e46307d726.zip
|  |  |  |- 📜 @types-d3-transition-npm-3.0.3-6b21cc91f7-ab9ce12510.zip
|  |  |  |- 📜 @adobe-css-tools-npm-4.3.1-8afe87e987-ad43456379.zip
|  |  |  |- 📜 deepmerge-npm-4.3.1-4f751a0844-2024c6a980.zip
|  |  |  |- 📜 make-error-npm-1.3.6-ccb85d9458-b86e5e0e25.zip
|  |  |  |- 📜 protocol-buffers-schema-npm-3.6.0-af2f375e69-8713b5770f.zip
|  |  |  |- 📜 glsl-resolve-npm-0.0.1-f1dbeec776-8bc83f4c56.zip
|  |  |  |- 📜 @lezer-python-npm-1.1.3-9b32c441a8-6c621b8970.zip
|  |  |  |- 📜 is-regex-npm-1.1.4-cca193ef11-362399b335.zip
|  |  |  |- 📜 @types-d3-dispatch-npm-3.0.2-a1a4d1487b-716f21bdc4.zip
|  |  |  |- 📜 chart.js-npm-4.2.1-97512b9a29-7319fdfd1e.zip
|  |  |  |- 📜 reactflow-npm-11.7.4-c92d31baa6-c5178deb5d.zip
|  |  |  |- 📜 validate.io-integer-primitive-npm-1.0.0-52d6c33313-7f26d95b29.zip
|  |  |  |- 📜 @typescript-eslint-typescript-estree-npm-5.58.0-731f648727-51b668ec85.zip
|  |  |  |- 📜 gestalt-npm-101.3.9-0e644ced2e-33a382410a.zip
|  |  |  |- 📜 type-name-npm-2.0.2-71ed4934eb-747a850339.zip
|  |  |  |- 📜 murmurhash-js-npm-1.0.0-b1fa804bc0-083cea92a1.zip
|  |  |  |- 📜 @jridgewell-set-array-npm-1.1.2-45b82d7fb6-69a84d5980.zip
|  |  |  |- 📜 string.prototype.trim-npm-1.2.7-3fbaf3b9d2-05b7b2d6af.zip
|  |  |  |- 📜 streamsearch-npm-1.1.0-fc3ad6536d-1cce16cea8.zip
|  |  |  |- 📜 array-buffer-byte-length-npm-1.0.0-331671f28a-044e101ce1.zip
|  |  |  |- 📜 natural-compare-lite-npm-1.4.0-12b6b308ed-5222ac3986.zip
|  |  |  |- 📜 @types-d3-time-npm-3.0.0-9b0c5b0218-e76adb056d.zip
|  |  |  |- 📜 rimraf-npm-3.0.2-2cb7dac69a-87f4164e39.zip
|  |  |  |- 📜 globalthis-npm-1.0.3-96cd56020d-fbd7d760dc.zip
|  |  |  |- 📜 @protobufjs-inquire-npm-1.1.0-3c7759e9ce-ca06f02eaf.zip
|  |  |  |- 📜 @protobufjs-eventemitter-npm-1.1.0-029cc7d431-0369163a3d.zip
|  |  |  |- 📜 @babel-helper-string-parser-npm-7.19.4-0db110dc3a-b2f8a3920b.zip
|  |  |  |- 📜 @babel-template-npm-7.20.7-c157fc5838-2eb1a0ab8d.zip
|  |  |  |- 📜 type-npm-1.2.0-e67311c4b2-dae8c64f82.zip
|  |  |  |- 📜 to-px-npm-1.1.0-148e37608b-bb434716a7.zip
|  |  |  |- 📜 @types-d3-shape-npm-3.1.1-542f46cb78-8f1762ecde.zip
|  |  |  |- 📜 is-set-npm-2.0.2-7e9ba84a8c-b64343faf4.zip
|  |  |  |- 📜 jest-matcher-utils-npm-29.5.0-f255c78df4-1d3e8c746e.zip
|  |  |  |- 📜 superscript-text-npm-1.0.0-65ffaf6da8-4c43755435.zip
|  |  |  |- 📜 json-stable-stringify-without-jsonify-npm-1.0.1-b65772b28b-cff44156dd.zip
|  |  |  |- 📜 which-collection-npm-1.0.1-cd2c054585-c815bbd163.zip
|  |  |  |- 📜 form-data-npm-4.0.0-916facec2d-01135bf867.zip
|  |  |  |- 📜 font-measure-npm-1.2.2-e39507b7c3-2cc2ad1772.zip
|  |  |  |- 📜 is-alphanumerical-npm-1.0.4-c96dc6d674-e2e491acc1.zip
|  |  |  |- 📜 crelt-npm-1.0.5-6dad646a54-04a618c587.zip
|  |  |  |- 📜 typed-styles-npm-0.0.7-14151fdbae-36a6ad6bee.zip
|  |  |  |- 📜 debug-npm-3.2.7-754e818c7a-b3d8c59407.zip
|  |  |  |- 📜 react-redux-npm-8.0.5-9ff31aed95-a108f4f7ea.zip
|  |  |  |- 📜 jest-diff-npm-29.5.0-5c9573ed73-dfd0f4a299.zip
|  |  |  |- 📜 js-sdsl-npm-4.3.0-4f51b3ddb2-ce908257cf.zip
|  |  |  |- 📜 @firebase-app-check-interop-types-npm-0.2.0-e41cbc4913-6bbe23aa0b.zip
|  |  |  |- 📜 uncontrollable-npm-7.2.1-85b30af5c9-3345c0c191.zip
|  |  |  |- 📜 resolve-protobuf-schema-npm-2.1.0-56c0d37a08-88fffab2a3.zip
|  |  |  |- 📜 @typescript-eslint-utils-npm-5.58.0-3279680cff-c618ae6796.zip
|  |  |  |- 📜 d3-path-npm-1.0.9-84bf428111-d4382573ba.zip
|  |  |  |- 📜 react-clientside-effect-npm-1.2.6-4c95acf94f-7db6110027.zip
|  |  |  |- 📜 use-sidecar-npm-1.1.2-dfc322e94a-925d1922f9.zip
|  |  |  |- 📜 @firebase-performance-types-npm-0.2.0-48b008b42a-cf7c4ff4ee.zip
|  |  |  |- 📜 is-weakref-npm-1.0.2-ff80e8c314-95bd9a57cd.zip
|  |  |  |- 📜 immediate-npm-3.0.6-c27588a2d3-f9b3486477.zip
|  |  |  |- 📜 tslib-npm-2.5.0-bb364efebd-ae3ed5f9ce.zip
|  |  |  |- 📜 lodash.throttle-npm-4.1.1-856641af92-129c0a28ce.zip
|  |  |  |- 📜 @firebase-auth-compat-npm-0.3.5-54a7b491bd-9500b6fdc4.zip
|  |  |  |- 📜 stylis-npm-4.1.3-c3e2662f97-d04dbffcb9.zip
|  |  |  |- 📜 from2-npm-2.3.0-bd16dc410b-6080eba079.zip
|  |  |  |- 📜 inflight-npm-1.0.6-ccedb4b908-f4f76aa072.zip
|  |  |  |- 📜 isarray-npm-0.0.1-92e37e0a70-49191f1425.zip
|  |  |  |- 📜 is-fullwidth-code-point-npm-3.0.0-1ecf4ebee5-44a30c2945.zip
|  |  |  |- 📜 parse-rect-npm-1.2.0-163494166a-5abf383475.zip
|  |  |  |- 📜 @types-prop-types-npm-15.7.5-2aa48aa177-5b43b8b154.zip
|  |  |  |- 📜 parse-entities-npm-2.0.0-b7b4f46ff6-7addfd3e7d.zip
|  |  |  |- 📜 @types-react-is-npm-17.0.3-1deb53884e-6abb7c47d5.zip
|  |  |  |- 📜 glsl-token-string-npm-1.0.1-b01fad3c92-3260c1486b.zip
|  |  |  |- 📜 bit-twiddle-npm-1.0.2-b0a9a49684-2f97b47d75.zip
|  |  |  |- 📜 jsesc-npm-2.5.2-c5acb78804-4dc1907711.zip
|  |  |  |- 📜 postcss-npm-8.4.31-385051a82b-1d8611341b.zip
|  |  |  |- 📜 @mapbox-geojson-types-npm-1.0.2-062b8a47d3-ab1fa0afce.zip
|  |  |  |- 📜 raf-npm-3.4.1-c25d48d76e-50ba284e48.zip
|  |  |  |- 📜 @eslint-eslintrc-npm-2.0.1-a51f526c2a-56b9192a68.zip
|  |  |  |- 📜 csscolorparser-npm-1.0.3-cd8e162bc9-e40f3045ea.zip
|  |  |  |- 📜 @types-d3-drag-npm-3.0.2-d95a1da3b2-cd2fd6a628.zip
|  |  |  |- 📜 pick-by-alias-npm-1.2.0-fa40696855-720c85f13a.zip
|  |  |  |- 📜 parent-module-npm-1.0.1-1fae11b095-6ba8b25514.zip
|  |  |  |- 📜 @mapbox-jsonlint-lines-primitives-npm-2.0.2-f48e04c479-4eb31edd3c.zip
|  |  |  |- 📜 react-is-npm-18.2.0-0cc5edb910-e72d0ba81b.zip
|  |  |  |- 📜 object-inspect-npm-1.12.3-1e7d20f5ff-dabfd824d9.zip
|  |  |  |- 📜 busboy-npm-1.6.0-ebb5cbb04b-32801e2c01.zip
|  |  |  |- 📜 @types-d3-hierarchy-npm-3.1.2-6331916d86-fc423b2584.zip
|  |  |  |- 📜 eslint-scope-npm-5.1.1-71fe59b18a-47e4b6a3f0.zip
|  |  |  |- 📜 lodash.isplainobject-npm-4.0.6-d73937742f-29c6351f28.zip
|  |  |  |- 📜 @firebase-functions-compat-npm-0.3.4-2245522325-bbfb7aaffc.zip
|  |  |  |- 📜 @types-react-transition-group-npm-4.4.5-8f92107b07-265f1c7406.zip
|  |  |  |- 📜 ansi-styles-npm-5.2.0-72fc7003e3-d7f4e97ce0.zip
|  |  |  |- 📜 isexe-npm-2.0.0-b58870bd2e-26bf6c5480.zip
|  |  |  |- 📜 shallow-copy-npm-0.0.1-86f126ce91-2d249a5a57.zip
|  |  |  |- 📜 react-data-table-component-npm-7.5.3-74567c12a2-d17a85ad13.zip
|  |  |  |- 📜 css-font-stretch-keywords-npm-1.0.1-cab1590819-4c3bf449e8.zip
|  |  |  |- 📜 font-atlas-npm-2.1.0-5465cf378f-2a1309cf48.zip
|  |  |  |- 📜 lz-string-npm-1.5.0-3860794e30-1ee98b4580.zip
|  |  |  |- 📜 @humanwhocodes-object-schema-npm-1.2.1-eb622b5d0e-a824a1ec31.zip
|  |  |  |- 📜 react-calendly-npm-4.1.1-2a07a5a3bb-7c4953c8b1.zip
|  |  |  |- 📜 @types-long-npm-4.0.2-e7bdc00dd4-d16cde7240.zip
|  |  |  |- 📜 @plotly-d3-sankey-circular-npm-0.33.1-d95f530c62-cf1d7b1b70.zip
|  |  |  |- 📜 @types-gestalt-npm-101.0.0-8f776be142-93c9d0ba44.zip
|  |  |  |- 📜 glsl-inject-defines-npm-1.0.3-21098475e9-91d707cc4c.zip
|  |  |  |- 📜 wrappy-npm-1.0.2-916de4d4b3-159da4805f.zip
|  |  |  |- 📜 react-dom-npm-18.2.0-dd675bca1c-7d323310be.zip
|  |  |  |- 📜 faye-websocket-npm-0.11.4-1f0de76de9-d49a62caf0.zip
|  |  |  |- 📜 is-core-module-npm-2.11.0-70061e141a-f96fd490c6.zip
|  |  |  |- 📜 svg-path-bounds-npm-1.0.2-f67934f056-8590a4e149.zip
|  |  |  |- 📜 popper.js-npm-1.16.1-a99192bd83-c56ae5001e.zip
|  |  |  |- 📜 ci-info-npm-3.8.0-d56a0b67d6-d0a4d31604.zip
|  |  |  |- 📜 parse-unit-npm-1.0.1-23b0c1dc0d-fdd7d2b91a.zip
|  |  |  |- 📜 shebang-regex-npm-3.0.0-899a0cd65e-1a2bcae50d.zip
|  |  |  |- 📜 unquote-npm-1.1.1-11903c1689-71745867d0.zip
|  |  |  |- 📜 asynckit-npm-0.4.0-c718858525-7b78c451df.zip
|  |  |  |- 📜 @firebase-messaging-interop-types-npm-0.2.0-2dda9c2152-9e489bb4f5.zip
|  |  |  |- 📜 @firebase-app-check-npm-0.6.4-630c94a334-04b1a84223.zip
|  |  |  |- 📜 web-vitals-npm-2.1.4-68bdd9ecb2-03d3f47dbf.zip
|  |  |  |- 📜 estraverse-npm-5.3.0-03284f8f63-072780882d.zip
|  |  |  |- 📜 validate.io-positive-integer-npm-1.0.0-7d037ca6a1-00127f5379.zip
|  |  |  |- 📜 use-callback-ref-npm-1.3.0-6c0773783f-7913df383a.zip
|  |  |  |- 📜 require-directory-npm-2.1.1-8608aee50b-fb47e70bf0.zip
|  |  |  |- 📜 @types-d3-format-npm-3.0.1-1b079419e7-6819fae7e7.zip
|  |  |  |- 📜 color-rgba-npm-2.4.0-b26bc15fea-a72b1001af.zip
|  |  |  |- 📜 @mapbox-whoots-js-npm-3.1.0-25c0fa7510-c1837c04ef.zip
|  |  |  |- 📜 doctrine-npm-3.0.0-c6f1615f04-fd7673ca77.zip
|  |  |  |- 📜 arr-flatten-npm-1.1.0-0c12b693e4-963fe12564.zip
|  |  |  |- 📜 jszip-npm-3.10.1-2862546cfb-abc77bfbe3.zip
|  |  |  |- 📜 d3-force-npm-1.2.1-19e909f60f-b73fe29d6c.zip
|  |  |  |- 📜 lru-cache-npm-6.0.0-b4c8668fe1-f97f499f89.zip
|  |  |  |- 📜 object-assign-npm-4.1.1-1004ad6dec-fcc6e4ea8c.zip
|  |  |  |- 📜 @firebase-firestore-types-npm-2.5.1-c5ca3659a6-2ad6f26d9d.zip
|  |  |  |- 📜 mouse-change-npm-1.4.0-a5ba0a76e7-67f7e5c7e2.zip
|  |  |  |- 📜 @nodelib-fs.scandir-npm-2.1.5-89c67370dd-a970d595bd.zip
|  |  |  |- 📜 @types-use-sync-external-store-npm-0.0.3-875a91a914-161ddb8eec.zip
|  |  |  |- 📜 @types-d3-force-npm-3.0.4-1a7cd542f1-779fb597fb.zip
|  |  |  |- 📜 chartjs-adapter-date-fns-npm-3.0.0-42916eb5be-c39bfdf490.zip
|  |  |  |- 📜 has-npm-1.0.3-b7f00631c1-b9ad53d53b.zip
|  |  |  |- 📜 @emotion-babel-plugin-npm-11.10.6-acad1f59fe-3eed138932.zip
|  |  |  |- 📜 @reactflow-node-toolbar-npm-1.2.3-17f071a25e-09d8102190.zip
|  |  |  |- 📜 @eslint-community-eslint-utils-npm-4.3.0-4ed2f1d6c5-f487760a69.zip
|  |  |  |- 📜 socket.io-parser-npm-4.2.4-bf87f78bcd-61540ef99a.zip
|  |  |  |- 📜 @types-d3-timer-npm-3.0.0-b8c95909c6-1ec86b3808.zip
|  |  |  |- 📜 @firebase-auth-npm-0.21.5-5d6806467f-154c97a2fe.zip
|  |  |  |- 📜 brace-expansion-npm-1.1.11-fb95eb05ad-faf34a7bb0.zip
|  |  |  |- 📜 probe-image-size-npm-7.2.3-2b6ee36e6f-1a5eeb8f5c.zip
|  |  |  |- 📜 glslify-bundle-npm-5.1.1-dc35401961-e3a5e438dd.zip
|  |  |  |- 📜 flip-pixels-npm-1.0.2-559f77073e-bf5308eba5.zip
|  |  |  |- 📜 @firebase-remote-config-types-npm-0.3.0-f86a82d8d8-3ce1b3f17d.zip
|  |  |  |- 📜 @codemirror-theme-one-dark-npm-6.1.1-9bdc2a6ad9-e314033c77.zip
|  |  |  |- 📜 @codemirror-lint-npm-6.2.0-d2556257f7-b97e55a07b.zip
|  |  |  |- 📜 core-util-is-npm-1.0.3-ca74b76c90-9de8597363.zip
|  |  |  |- 📜 regl-npm-2.1.0-12a0de3f80-dd890b7f50.zip
|  |  |  |- 📜 d3-hierarchy-npm-1.1.9-815cf44704-5fd8761c30.zip
|  |  |  |- 📜 @types-d3-quadtree-npm-3.0.2-3f2f06169f-2a831a8059.zip
|  |  |  |- 📜 esquery-npm-1.5.0-d8f8a06879-aefb0d2596.zip
|  |  |  |- 📜 shallowequal-npm-1.1.0-6688d419cb-f4c1de0837.zip
|  |  |  |- 📜 @dnd-kit-core-npm-6.0.8-66053fe203-abe48ff739.zip
|  |  |  |- 📜 ext-npm-1.7.0-580588ab93-ef481f9ef4.zip
|  |  |  |- 📜 @emotion-unitless-npm-0.8.0-aa125284fa-176141117e.zip
|  |  |  |- 📜 @codemirror-autocomplete-npm-6.4.2-e230a7fe53-c6cc4edb1c.zip
|  |  |  |- 📜 type-check-npm-0.4.0-60565800ce-ec688ebfc9.zip
|  |  |  |- 📜 prismjs-npm-1.29.0-6faa5b04b8-007a8869d4.zip
|  |  |  |- 📜 @firebase-firestore-npm-3.9.0-bfe733d8ba-9d448bf6bd.zip
|  |  |  |- 📜 globals-npm-11.12.0-1fa7f41a6c-67051a45ec.zip
|  |  |  |- 📜 @next-swc-darwin-arm64-npm-14.0.1-7ce7fc3362-8.zip
|  |  |  |- 📜 object.hasown-npm-1.1.2-db9bbc7f97-b936572536.zip
|  |  |  |- 📜 d3-shape-npm-1.3.7-8220c839bc-46566a3ab6.zip
|  |  |  |- 📜 d3-timer-npm-3.0.1-45083f465d-1cfddf86d7.zip
|  |  |  |- 📜 is-decimal-npm-1.0.4-e67dbd40dd-ed483a3875.zip
|  |  |  |- 📜 signum-npm-1.0.0-e76444a4d9-f045c95499.zip
|  |  |  |- 📜 @babel-helper-module-imports-npm-7.18.6-1031faa864-f393f8a3b3.zip
|  |  |  |- 📜 svg-path-sdf-npm-1.1.3-88621dc0b9-34cb031e12.zip
|  |  |  |- 📜 ieee754-npm-1.2.1-fb63b3caeb-5144c0c981.zip
|  |  |  |- 📜 array.prototype.flatmap-npm-1.3.1-c65186ca34-8c1c43a499.zip
|  |  |  |- 📜 @types-d3-dsv-npm-3.0.1-a476986190-f3dbb3c994.zip
|  |  |  |- 📜 d3-dispatch-npm-1.0.6-afea222924-b4ecb016b6.zip
|  |  |  |- 📜 dom-accessibility-api-npm-0.5.16-d3e2310666-005eb283ca.zip
|  |  |  |- 📜 redent-npm-3.0.0-31892f4906-fa1ef20404.zip
|  |  |  |- 📜 @dnd-kit-sortable-npm-7.0.2-8871eace61-4ce705aceb.zip
|  |  |  |- 📜 react-async-script-npm-1.2.0-e56221a5f4-303890eeaf.zip
|  |  |  |- 📜 @types-react-csv-npm-1.1.3-0bb165e31d-1b4b131bf7.zip
|  |  |  |- 📜 ms-npm-2.1.3-81ff3cfac1-aa92de6080.zip
|  |  |  |- 📜 draw-svg-path-npm-1.0.0-f2eaf99e26-d1f6b79791.zip
|  |  |  |- 📜 clamp-npm-1.0.1-9fe98d4de3-799bd70837.zip
|  |  |  |- 📜 date-fns-npm-2.29.3-fef7e3c72c-e01cf5b62a.zip
|  |  |  |- 📜 protobufjs-npm-7.2.4-c40bd79e8d-a952cdf2a5.zip
|  |  |  |- 📜 codepage-npm-1.15.0-bde3a4eb54-86bdfd8f8f.zip
|  |  |  |- 📜 typedarray-pool-npm-1.2.0-177bbf7834-dbba84b83f.zip
|  |  |  |- 📜 @uiw-codemirror-extensions-basic-setup-npm-4.19.9-fe498b7c1b-f248d1623f.zip
|  |  |  |- 📜 flatten-vertex-data-npm-1.0.2-57711ba8aa-45757b5f02.zip
|  |  |  |- 📜 @mapbox-vector-tile-npm-1.3.1-c7cbcaf846-7093d4fa7d.zip
|  |  |  |- 📜 @reactflow-node-resizer-npm-2.1.1-838a04869a-f820d3e738.zip
|  |  |  |- 📜 rc-util-npm-5.29.2-62ac7967b2-68c6bcf2bd.zip
|  |  |  |- 📜 pretty-format-npm-29.5.0-4f1086147d-4065356b55.zip
|  |  |  |- 📜 @types-d3-contour-npm-3.0.2-c4ee34fb06-7b0f7ccf33.zip
|  |  |  |- 📜 @types-file-saver-npm-2.0.5-b1e5b3252c-a31d6ee2ab.zip
|  |  |  |- 📜 gopd-npm-1.0.1-10c1d0b534-a5ccfb8806.zip
|  |  |  |- 📜 safe-regex-test-npm-1.0.0-e94a09b84e-bc566d8beb.zip
|  |  |  |- 📜 @types-hoist-non-react-statics-npm-3.3.1-c0081332b2-2c0778570d.zip
|  |  |  |- 📜 duplexify-npm-3.7.1-8f4f1e821f-3c2ed2223d.zip
|  |  |  |- 📜 normalize-svg-path-npm-1.1.0-6094833661-106e108b2f.zip
|  |  |  |- 📜 @kurkle-color-npm-0.3.2-98f2086013-79e97b31f8.zip
|  |  |  |- 📜 is-browser-npm-2.1.0-bbc8fdc4ed-fe8d9a68d0.zip
|  |  |  |- 📜 d-npm-1.0.1-64afbbc689-49ca0639c7.zip
|  |  |  |- 📜 regl-scatter2d-npm-3.2.8-a9af151462-5f931fb2cd.zip
|  |  |  |- 📜 type-fest-npm-0.20.2-b36432617f-4fb3272df2.zip
|  |  |  |- 📜 d3-time-npm-1.1.0-5df1aeb229-33fcfff94f.zip
|  |  |  |- 📜 strip-json-comments-npm-3.1.1-dcb2324823-492f73e272.zip
|  |  |  |- 📜 @firebase-messaging-npm-0.12.4-1b82792ae1-08787e0c0d.zip
|  |  |  |- 📜 process-nextick-args-npm-2.0.1-b8d7971609-1d38588e52.zip
|  |  |  |- 📜 argparse-npm-2.0.1-faff7999e6-83644b5649.zip
|  |  |  |- 📜 @typescript-eslint-parser-npm-5.58.0-6b3789fcc1-38681da48a.zip
|  |  |  |- 📜 es-to-primitive-npm-1.2.1-b7a7eac6c5-4ead6671a2.zip
|  |  |  |- 📜 functions-have-names-npm-1.2.3-e5cf1e2208-c3f1f5ba20.zip
|  |  |  |- 📜 type-check-npm-0.3.2-a4a38bb0b6-dd3b149564.zip
|  |  |  |- 📜 grapheme-splitter-npm-1.0.4-648f2bf509-0c22ec54de.zip
|  |  |  |- 📜 elementary-circuits-directed-graph-npm-1.3.1-43e3cfa4d3-e88536739a.zip
|  |  |  |- 📜 estraverse-npm-4.3.0-920a32f3c6-a6299491f9.zip
|  |  |  |- 📜 @turf-centroid-npm-6.5.0-99d1e4024e-1a37c26232.zip
|  |  |  |- 📜 chalk-npm-2.4.2-3ea16dd91e-ec3661d38f.zip
|  |  |  |- 📜 is-callable-npm-1.2.7-808a303e61-61fd57d03b.zip
|  |  |  |- 📜 js-tokens-npm-4.0.0-0ac852e9e2-8a95213a5a.zip
|  |  |  |- 📜 eslint-scope-npm-7.1.1-23935eb377-9f6e974ab2.zip
|  |  |  |- 📜 @mui-utils-npm-5.11.13-b71980ec12-0f403f2635.zip
|  |  |  |- 📜 is-obj-npm-1.0.1-7d391539d7-3ccf0efdea.zip
|  |  |  |- 📜 cfb-npm-1.2.2-df6fc7d448-cfb63a7d63.zip
|  |  |  |- 📜 callsites-npm-3.1.0-268f989910-072d17b6ab.zip
|  |  |  |- 📜 mouse-event-npm-1.0.5-8b413267f1-1e7fa5deb6.zip
|  |  |  |- 📜 react-npm-18.2.0-1eae08fee2-88e38092da.zip
|  |  |  |- 📜 react-bootstrap-npm-2.7.2-93727ae0c4-656c0c5e44.zip
|  |  |  |- 📜 file-saver-npm-2.0.5-2c3bc40d53-c62d96e5ce.zip
|  |  |  |- 📜 engine.io-parser-npm-5.0.6-6021cc2c82-e92255b546.zip
|  |  |  |- 📜 object.assign-npm-4.1.4-fb3deb1c3a-76cab513a5.zip
|  |  |  |- 📜 fill-range-npm-7.0.1-b8b1817caa-cc283f4e65.zip
|  |  |  |- 📜 @babel-highlight-npm-7.18.6-9d35ad2e27-92d8ee6154.zip
|  |  |  |- 📜 nanoid-npm-5.0.1-3b97be5eee-fb5a57ec05.zip
|  |  |  |- 📜 is-iexplorer-npm-1.0.0-0fcfb101e8-cc6c14c460.zip
|  |  |  |- 📜 @types-stack-utils-npm-2.0.1-867718ab70-205fdbe332.zip
|  |  |  |- 📜 number-is-integer-npm-1.0.1-7bdfc19de0-6cbe30d839.zip
|  |  |  |- 📜 resolve-from-npm-4.0.0-f758ec21bf-f4ba0b8494.zip
|  |  |  |- 📜 @types-aria-query-npm-5.0.1-5c01a56741-69fd7cceb6.zip
|  |  |  |- 📜 @mapbox-unitbezier-npm-0.0.0-159cc70ee6-22ae6d56f7.zip
|  |  |  |- 📜 is-base64-npm-0.1.0-f96c200cfb-7a6b70e68a.zip
|  |  |  |- 📜 glslify-npm-7.1.1-035a14381b-2bb59c0480.zip
|  |  |  |- 📜 @emotion-sheet-npm-1.2.1-ede8a680b2-ce78763588.zip
|  |  |  |- 📜 array-includes-npm-3.1.6-d0ff9d248b-f22f8cd8ba.zip
|  |  |  |- 📜 @lezer-common-npm-1.0.2-0f6180d7ec-bbcc58e07b.zip
|  |  |  |- 📜 stack-utils-npm-2.0.6-2be1099696-052bf4d25b.zip
|  |  |  |- 📜 flatted-npm-3.2.7-0da10b7c56-427633049d.zip
|  |  |  |- 📜 @typescript-eslint-types-npm-5.58.0-6a148547b0-8622a73d73.zip
|  |  |  |- 📜 @emotion-cache-npm-11.10.5-e5bc83f178-1dd2d9af2d.zip
|  |  |  |- 📜 react-focus-lock-npm-2.9.4-395896aa07-f4c696bdbd.zip
|  |  |  |- 📜 is-string-npm-1.0.7-9f7066daed-323b3d0462.zip
|  |  |  |- 📜 @types-d3-delaunay-npm-6.0.1-32a8c6cbed-c46fd6f399.zip
|  |  |  |- 📜 @firebase-component-npm-0.6.4-3592a60aed-5d7006e4bc.zip
|  |  |  |- 📜 graceful-fs-npm-4.2.11-24bb648a68-ac85f94da9.zip
|  |  |  |- 📜 @firebase-app-check-compat-npm-0.3.4-3706236dc4-e9fa728fed.zip
|  |  |  |- 📜 micromatch-npm-4.0.5-cfab5d7669-02a17b671c.zip
|  |  |  |- 📜 @emotion-utils-npm-1.2.0-337992f692-55457a49dd.zip
|  |  |  |- 📜 hastscript-npm-6.0.0-380b27a9f0-5e50b85af0.zip
|  |  |  |- 📜 color-parse-npm-1.3.8-5218d57572-181ede6955.zip
|  |  |  |- 📜 setimmediate-npm-1.0.5-54587459b6-c9a6f2c5b5.zip
|  |  |  |- 📜 @emotion-styled-npm-11.10.6-b860023bfd-ed0ee4bec3.zip
|  |  |  |- 📜 @emotion-react-npm-11.10.6-655b70ad8d-4762042e39.zip
|  |  |  |- 📜 engine.io-client-npm-6.4.0-614bfea593-f412a5d490.zip
|  |  |  |- 📜 object.entries-npm-1.1.6-5f9ba14b46-0f8c47517e.zip
|  |  |  |- 📜 is-array-buffer-npm-3.0.2-0dec897785-dcac9dda66.zip
|  |  |  |- 📜 side-channel-npm-1.0.4-e1f38b9e06-351e41b947.zip
|  |  |  |- 📜 @typescript-eslint-type-utils-npm-5.58.0-6f2392c10d-803f24daed.zip
|  |  |  |- 📜 glsl-token-defines-npm-1.0.0-bd3da98093-79c3738e4c.zip
|  |  |  |- 📜 validate.io-string-primitive-npm-1.0.1-7763f9c1ec-7c4c542ab9.zip
|  |  |  |- 📜 glsl-token-assignments-npm-2.0.2-d9ee3ee3f3-efd6051cfd.zip
|  |  |  |- 📜 to-float32-npm-1.1.0-e7613af8a0-aff308bbc7.zip
|  |  |  |- 📜 is-arrayish-npm-0.2.1-23927dfb15-eef4417e3c.zip
|  |  |  |- 📜 es6-weak-map-npm-2.0.3-5e57e0b4e6-19ca15f46d.zip
|  |  |  |- 📜 y18n-npm-5.0.8-5f3a0a7e62-54f0fb9562.zip
|  |  |  |- 📜 next-redux-wrapper-npm-8.1.0-3800723e43-74fa213550.zip
|  |  |  |- 📜 typed-array-length-npm-1.0.4-92771b81fc-2228febc93.zip
|  |  |  |- 📜 ssf-npm-0.11.2-e6437eb624-6ecef6ae0a.zip
|  |  |  |- 📜 @types-semver-npm-7.3.13-56212b60da-00c0724d54.zip
|  |  |  |- 📜 @reduxjs-toolkit-npm-1.9.3-cbad5da1de-d965fc6197.zip
|  |  |  |- 📜 merge2-npm-1.4.1-a2507bd06c-7268db63ed.zip
|  |  |  |- 📜 @testing-library-user-event-npm-13.5.0-1ff89b703a-16319de685.zip
|  |  |  |- 📜 @firebase-webchannel-wrapper-npm-0.9.0-f331ec8b01-a4729e974c.zip
|  |  |  |- 📜 local-storage-fallback-npm-4.1.2-21ab2bad74-d24d4c125c.zip
|  |  |  |- 📜 eslint-npm-8.36.0-f8482bce95-e9a961fc3b.zip
|  |  |  |- 📜 @firebase-app-types-npm-0.9.0-c08aff84f3-e79bd3c4a8.zip
|  |  |  |- 📜 lodash.merge-npm-4.6.2-77cb4416bf-ad580b4bdb.zip
|  |  |  |- 📜 yocto-queue-npm-0.1.0-c6c9a7db29-f77b3d8d00.zip
|  |  |  |- 📜 wmf-npm-1.0.2-15d4e3e93c-d336acb2c7.zip
|  |  |  |- 📜 d3-zoom-npm-3.0.0-18f706a421-8056e35272.zip
|  |  |  |- 📜 react-onclickoutside-npm-6.12.2-61c80f0d9a-a0c7f4fbcf.zip
|  |  |  |- 📜 @plotly-point-cluster-npm-3.1.9-9ab3edb250-14056dbf1c.zip
|  |  |  |- 📜 @testing-library-dom-npm-9.0.1-a05e7f233d-fa3d4097d0.zip
|  |  |  |- 📜 @types-d3-fetch-npm-3.0.2-7176983808-10fad5c1d4.zip
|  |  |  |- 📜 iconv-lite-npm-0.4.24-c5c4ac6695-bd9f120f5a.zip
|  |  |  |- 📜 hast-util-parse-selector-npm-2.2.5-cd773533ea-22ee4afbd1.zip
|  |  |  |- 📜 typescript-patch-7ee4c41060-bdbf3d0aac.zip
|  |  |  |- 📜 @jridgewell-gen-mapping-npm-0.3.2-c64eeb4a4e-1832707a1c.zip
|  |  |  |- 📜 globby-npm-11.1.0-bdcdf20c71-b4be8885e0.zip
|  |  |  |- 📜 d3-interpolate-npm-3.0.1-77ddca7977-a42ba314e2.zip
|  |  |- 📜 install-state.gz
|  |- 📂 layer_docs:
|  |  |- 📜 Linear.md : Doc for Linear layer
|  |  |- 📜 ReLU.md : Doc for ReLU later
|  |  |- 📜 softmax_equation.png : PNG file of Softmax equation
|  |  |- 📜 Softmax.md : Doc for Softmax layer
|  |- 📂 src:
|  |  |- 📂 pages:
|  |  |  |- 📂 train:
|  |  |  |  |- 📜 index.tsx
|  |  |  |  |- 📜 [train_space_id].tsx
|  |  |  |- 📜 _app.tsx
|  |  |  |- 📜 _document.tsx
|  |  |  |- 📜 LearnContent.tsx
|  |  |  |- 📜 wiki.tsx
|  |  |  |- 📜 learn.tsx
|  |  |  |- 📜 forgot.tsx
|  |  |  |- 📜 settings.tsx
|  |  |  |- 📜 dashboard.tsx
|  |  |  |- 📜 login.tsx
|  |  |  |- 📜 about.tsx
|  |  |  |- 📜 feedback.tsx
|  |  |- 📂 common:
|  |  |  |- 📂 styles:
|  |  |  |  |- 📜 globals.css
|  |  |  |  |- 📜 Home.module.css
|  |  |  |- 📂 redux:
|  |  |  |  |- 📜 userLogin.ts
|  |  |  |  |- 📜 backendApi.ts
|  |  |  |  |- 📜 store.ts
|  |  |  |  |- 📜 hooks.ts
|  |  |  |  |- 📜 train.ts
|  |  |  |- 📂 utils:
|  |  |  |  |- 📜 dndHelpers.ts
|  |  |  |  |- 📜 firebase.ts
|  |  |  |  |- 📜 dateFormat.ts
|  |  |  |- 📂 components:
|  |  |  |  |- 📜 Spacer.tsx
|  |  |  |  |- 📜 Footer.tsx
|  |  |  |  |- 📜 HtmlTooltip.tsx
|  |  |  |  |- 📜 DlpTooltip.tsx
|  |  |  |  |- 📜 ClientOnlyPortal.tsx
|  |  |  |  |- 📜 NavBarMain.tsx
|  |  |  |  |- 📜 EmailInput.tsx
|  |  |  |  |- 📜 TitleText.tsx
|  |  |- 📂 backend_outputs:
|  |  |  |- 📜 my_deep_learning_model.onnx : Last ONNX file output
|  |  |  |- 📜 model.pt : Last model.pt output
|  |  |  |- 📜 model.pkl
|  |  |- 📂 features:
|  |  |  |- 📂 Train:
|  |  |  |  |- 📂 redux:
|  |  |  |  |  |- 📜 trainspaceSlice.ts
|  |  |  |  |  |- 📜 trainspaceApi.ts
|  |  |  |  |- 📂 features:
|  |  |  |  |  |- 📂 Image:
|  |  |  |  |  |  |- 📂 redux:
|  |  |  |  |  |  |  |- 📜 imageActions.ts
|  |  |  |  |  |  |  |- 📜 imageApi.ts
|  |  |  |  |  |  |- 📂 types:
|  |  |  |  |  |  |  |- 📜 imageTypes.ts
|  |  |  |  |  |  |- 📂 constants:
|  |  |  |  |  |  |  |- 📜 imageConstants.ts
|  |  |  |  |  |  |- 📂 components:
|  |  |  |  |  |  |  |- 📜 ImageParametersStep.tsx
|  |  |  |  |  |  |  |- 📜 ImageTrainspace.tsx
|  |  |  |  |  |  |  |- 📜 ImageFlow.tsx
|  |  |  |  |  |  |  |- 📜 ImageDatasetStep.tsx
|  |  |  |  |  |  |  |- 📜 ImageReviewStep.tsx
|  |  |  |  |  |  |- 📜 index.ts
|  |  |  |  |  |- 📂 Tabular:
|  |  |  |  |  |  |- 📂 redux:
|  |  |  |  |  |  |  |- 📜 tabularActions.ts
|  |  |  |  |  |  |  |- 📜 tabularApi.ts
|  |  |  |  |  |  |- 📂 types:
|  |  |  |  |  |  |  |- 📜 tabularTypes.ts
|  |  |  |  |  |  |- 📂 constants:
|  |  |  |  |  |  |  |- 📜 tabularConstants.ts
|  |  |  |  |  |  |- 📂 components:
|  |  |  |  |  |  |  |- 📜 TabularParametersStep.tsx
|  |  |  |  |  |  |  |- 📜 TabularTrainspace.tsx
|  |  |  |  |  |  |  |- 📜 TabularDatasetStep.tsx
|  |  |  |  |  |  |  |- 📜 TabularReviewStep.tsx
|  |  |  |  |  |  |  |- 📜 TabularFlow.tsx
|  |  |  |  |  |  |- 📜 index.ts
|  |  |  |  |- 📂 types:
|  |  |  |  |  |- 📜 trainTypes.ts
|  |  |  |  |- 📂 constants:
|  |  |  |  |  |- 📜 trainConstants.ts
|  |  |  |  |- 📂 components:
|  |  |  |  |  |- 📜 CreateTrainspace.tsx
|  |  |  |  |  |- 📜 TrainspaceLayout.tsx
|  |  |  |  |  |- 📜 DatasetStepLayout.tsx
|  |  |  |- 📂 OpenAi:
|  |  |  |  |- 📜 openAiUtils.ts
|  |  |  |- 📂 Dashboard:
|  |  |  |  |- 📂 redux:
|  |  |  |  |  |- 📜 dashboardApi.ts
|  |  |  |  |- 📂 components:
|  |  |  |  |  |- 📜 TrainBarChart.tsx
|  |  |  |  |  |- 📜 TrainDataGrid.tsx
|  |  |  |  |  |- 📜 TrainDoughnutChart.tsx
|  |  |  |- 📂 Feedback:
|  |  |  |  |- 📂 redux:
|  |  |  |  |  |- 📜 feedbackApi.ts
|  |  |  |- 📂 LearnMod:
|  |  |  |  |- 📜 FRQuestion.tsx
|  |  |  |  |- 📜 LearningModulesContent.tsx
|  |  |  |  |- 📜 ModulesSideBar.tsx
|  |  |  |  |- 📜 MCQuestion.tsx
|  |  |  |  |- 📜 ClassCard.tsx
|  |  |  |  |- 📜 ImageComponent.tsx
|  |  |  |  |- 📜 Exercise.tsx
|  |  |- 📜 next-env.d.ts
|  |  |- 📜 iris.csv : Sample CSV data
|  |  |- 📜 GlobalStyle.ts
|  |  |- 📜 constants.ts
|  |- 📜 next-env.d.ts
|  |- 📜 tsconfig.json
|  |- 📜 next.config.js
|  |- 📜 yarn.lock
|  |- 📜 jest.config.js
|  |- 📜 .eslintrc.json
|  |- 📜 package.json
|  |- 📜 .eslintignore
```

