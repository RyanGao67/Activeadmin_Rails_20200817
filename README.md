```
bundle add activeadmin
bundle add devise
rails g active_admin:install
Running via Spring preloader in process 672042
      invoke  devise
    generate    devise:install
      create    config/initializers/devise.rb
      create    config/locales/devise.en.yml
  ===============================================================================

Depending on your application's configuration some manual setup may be required:

  1. Ensure you have defined default url options in your environments files. Here
     is an example of default_url_options appropriate for a development environment
     in config/environments/development.rb:

       config.action_mailer.default_url_options = { host: 'localhost', port: 3000 }

     In production, :host should be set to the actual host of your application.

     * Required for all applications. *

  2. Ensure you have defined root_url to *something* in your config/routes.rb.
     For example:

       root to: "home#index"
     
     * Not required for API-only Applications *

  3. Ensure you have flash messages in app/views/layouts/application.html.erb.
     For example:

       <p class="notice"><%= notice %></p>
       <p class="alert"><%= alert %></p>

     * Not required for API-only Applications *

  4. You can copy Devise views (for customization) to your app by running:

       rails g devise:views
       
     * Not required *

===============================================================================
      invoke    active_record
      create      db/migrate/20210818004640_devise_create_admin_users.rb
      create      app/models/admin_user.rb
      invoke      test_unit
      create        test/models/admin_user_test.rb
      create        test/fixtures/admin_users.yml
      insert      app/models/admin_user.rb
       route    devise_for :admin_users
        gsub    app/models/admin_user.rb
        gsub    config/routes.rb
      append    db/seeds.rb
      create  config/initializers/active_admin.rb
      create  app/admin
      create  app/admin/dashboard.rb
      create  app/admin/admin_users.rb
      insert  config/routes.rb
    generate  active_admin:assets
       rails  generate active_admin:assets 
Running via Spring preloader in process 672064
      create  app/assets/javascripts/active_admin.js
      create  app/assets/stylesheets/active_admin.scss
      create  db/migrate/20210818004642_create_active_admin_comments.rb
rails db:migrate
== 20210818004640 DeviseCreateAdminUsers: migrating ===========================
-- create_table(:admin_users)
   -> 0.0059s
-- add_index(:admin_users, :email, {:unique=>true})
   -> 0.0066s
-- add_index(:admin_users, :reset_password_token, {:unique=>true})
   -> 0.0016s
== 20210818004640 DeviseCreateAdminUsers: migrated (0.0144s) ==================

== 20210818004642 CreateActiveAdminComments: migrating ========================
-- create_table(:active_admin_comments)
   -> 0.0173s
-- add_index(:active_admin_comments, [:namespace])
   -> 0.0029s
== 20210818004642 CreateActiveAdminComments: migrated (0.0206s) ===============

rails g model Subject name
Running via Spring preloader in process 672201
      invoke  active_record
      create    db/migrate/20210818004740_create_subjects.rb
      create    app/models/subject.rb
      invoke    test_unit
      create      test/models/subject_test.rb
      create      test/fixtures/subjects.yml
      
      
rails db:migrate
== 20210818004740 CreateSubjects: migrating ===================================
-- create_table(:subjects)
   -> 0.0048s
== 20210818004740 CreateSubjects: migrated (0.0054s) ==========================

rails g active_admin:resource Subject
Running via Spring preloader in process 672317
      create  app/admin/subjects.rb


rails g model note title body:text subject:belongs_to

rails db:migrate

rails g active_admin:resource subject
Running via Spring preloader in process 674624
   identical  app/admin/subjects.rb

 
rails g active_admin:resource note
admin:resource note
Running via Spring preloader in process 674677
      create  app/admin/notes.rb


rails db:seed


 bundle add activeadmin_quill_editor
```
