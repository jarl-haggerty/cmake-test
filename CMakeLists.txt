cmake_minimum_required(VERSION 3.10)
project(ThorImageCMake LANGUAGES CXX CSharp)

include(CSharpUtilities)

if(NOT DEFINED CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE Debug)
endif()

add_library(One SHARED
  "One/UserControl1.xaml"
  "One/UserControl1.xaml.cs")
set_property(TARGET One PROPERTY VS_DOTNET_REFERENCES
  PresentationCore
  PresentationFramework
  System
  System.Core
  System.Data
  System.Data.DataSetExtensions
  System.Xaml
  System.Xml
  System.Xml.Linq
  WindowsBase)
set_property(TARGET One PROPERTY VS_DOTNET_TARGET_FRAMEWORK_VERSION "v4.8")

add_library(Two SHARED
  "Two/UserControl1.xaml"
  "Two/UserControl1.xaml.cs")
set_property(TARGET Two PROPERTY VS_DOTNET_REFERENCES
  PresentationCore
  PresentationFramework
  System
  System.Core
  System.Data
  System.Data.DataSetExtensions
  System.Xaml
  System.Xml
  System.Xml.Linq
  WindowsBase)
set_property(TARGET Two PROPERTY VS_DOTNET_TARGET_FRAMEWORK_VERSION "v4.8")