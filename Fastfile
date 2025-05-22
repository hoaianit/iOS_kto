default_platform(:ios)

platform :ios do
  desc "Build and upload to TestFlight"
  lane :release do
    build_app(
      workspace: "KhoaTuOnline.xcworkspace",
      scheme: "KhoaTuOnline",
      export_method: "app-store",
      output_name: "App.ipa"
    )

    app_store_connect_api_key(
      key_id: ENV["APP_STORE_KEY_ID"],
      issuer_id: ENV["APP_STORE_ISSUER_ID"],
      key_content: ENV["APP_STORE_KEY"],
      is_key_content_base64: true
    )

    upload_to_testflight
  end
end
