ADD_EXECUTABLE(avg-sensor-demo avg-sensor-demo.cpp)
TARGET_LINK_LIBRARIES(avg-sensor-demo fh-ece21-toolcase)

ADD_EXECUTABLE(malloc-free malloc-free.cpp)

ADD_EXECUTABLE(data-logger data-logger.cpp)
TARGET_LINK_LIBRARIES(data-logger fh-ece21-toolcase)

ADD_EXECUTABLE(map map.cpp)

ADD_EXECUTABLE(data-logger-test data-logger-test.cpp)
TARGET_LINK_LIBRARIES(data-logger-test fh-ece21-toolcase fh-ece21-logger)

IF (${MOSQUITTO_FOUND})
  ADD_EXECUTABLE(mosquitto-publish-demo mosquitto-publish-demo.cpp)
  TARGET_LINK_LIBRARIES(mosquitto-publish-demo Mosquitto::Mosquitto)
ENDIF()

IF (${LIBGPIOD_FOUND})
  ADD_EXECUTABLE(libgpiod-get-single libgpiod-get-single.cpp)
  TARGET_LINK_LIBRARIES(libgpiod-get-single LibGIOD::LibGIOD)
ELSE()
  MESSAGE(WARNING "LIBGPIOD_FOUND is false")
ENDIF()
