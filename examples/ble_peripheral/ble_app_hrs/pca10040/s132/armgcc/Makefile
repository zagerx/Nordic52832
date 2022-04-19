PROJECT_NAME     := ble_app_hrs_pca10040_s132
TARGETS          := nrf52832_xxaa
BUILD := _build

PREFIX = arm-none-eabi-
CC = $(PREFIX)gcc
AS = $(PREFIX)gcc -x assembler-with-cpp
CP = $(PREFIX)objcopy
SZ = $(PREFIX)size
HEX = $(CP) -O ihex
BIN = $(CP) -O binary -S


SDK_ROOT := ../../../../../..
PROJ_DIR := ../../..

#$(BUILD)/nrf52832_xxaa.out : 


LINKER_SCRIPT := ble_app_hrs_gcc_nrf52.ld

S_SOURCES = $(SDK_ROOT)/modules/nrfx/mdk/gcc_startup_nrf52.S 
# Source files common to all targets
SRC_FILES += \
  $(SDK_ROOT)/components/libraries/crypto/backend/nrf_hw/nrf_hw_backend_init.c \
  $(SDK_ROOT)/components/libraries/crypto/backend/nrf_hw/nrf_hw_backend_rng.c \
  $(SDK_ROOT)/components/libraries/crypto/backend/nrf_hw/nrf_hw_backend_rng_mbedtls.c \
  $(SDK_ROOT)/integration/nrfx/legacy/nrf_drv_clock.c \
  $(SDK_ROOT)/integration/nrfx/legacy/nrf_drv_rng.c \
  $(SDK_ROOT)/integration/nrfx/legacy/nrf_drv_uart.c \
  $(SDK_ROOT)/modules/nrfx/soc/nrfx_atomic.c \
  $(SDK_ROOT)/modules/nrfx/drivers/src/nrfx_clock.c \
  $(SDK_ROOT)/modules/nrfx/drivers/src/nrfx_gpiote.c \
  $(SDK_ROOT)/modules/nrfx/drivers/src/prs/nrfx_prs.c \
  $(SDK_ROOT)/modules/nrfx/drivers/src/nrfx_rng.c \
  $(SDK_ROOT)/modules/nrfx/drivers/src/nrfx_uart.c \
  $(SDK_ROOT)/modules/nrfx/drivers/src/nrfx_uarte.c \
  $(SDK_ROOT)/modules/nrfx/mdk/system_nrf52.c \
  $(SDK_ROOT)/components/libraries/button/app_button.c \
  $(SDK_ROOT)/components/libraries/util/app_error.c \
  $(SDK_ROOT)/components/libraries/util/app_error_handler_gcc.c \
  $(SDK_ROOT)/components/libraries/util/app_error_weak.c \
  $(SDK_ROOT)/components/libraries/scheduler/app_scheduler.c \
  $(SDK_ROOT)/components/libraries/timer/app_timer2.c \
  $(SDK_ROOT)/components/libraries/util/app_util_platform.c \
  $(SDK_ROOT)/components/libraries/crc16/crc16.c \
  $(SDK_ROOT)/components/libraries/timer/drv_rtc.c \
  $(SDK_ROOT)/components/libraries/fds/fds.c \
  $(SDK_ROOT)/components/libraries/hardfault/hardfault_implementation.c \
  $(SDK_ROOT)/components/libraries/mem_manager/mem_manager.c \
  $(SDK_ROOT)/components/libraries/util/nrf_assert.c \
  $(SDK_ROOT)/components/libraries/atomic_fifo/nrf_atfifo.c \
  $(SDK_ROOT)/components/libraries/atomic_flags/nrf_atflags.c \
  $(SDK_ROOT)/components/libraries/atomic/nrf_atomic.c \
  $(SDK_ROOT)/components/libraries/balloc/nrf_balloc.c \
  $(SDK_ROOT)/external/fprintf/nrf_fprintf.c \
  $(SDK_ROOT)/external/fprintf/nrf_fprintf_format.c \
  $(SDK_ROOT)/components/libraries/fstorage/nrf_fstorage.c \
  $(SDK_ROOT)/components/libraries/fstorage/nrf_fstorage_sd.c \
  $(SDK_ROOT)/components/libraries/memobj/nrf_memobj.c \
  $(SDK_ROOT)/components/libraries/pwr_mgmt/nrf_pwr_mgmt.c \
  $(SDK_ROOT)/components/libraries/queue/nrf_queue.c \
  $(SDK_ROOT)/components/libraries/ringbuf/nrf_ringbuf.c \
  $(SDK_ROOT)/components/libraries/experimental_section_vars/nrf_section_iter.c \
  $(SDK_ROOT)/components/libraries/sortlist/nrf_sortlist.c \
  $(SDK_ROOT)/components/libraries/strerror/nrf_strerror.c \
  $(SDK_ROOT)/components/libraries/sensorsim/sensorsim.c \
  $(SDK_ROOT)/components/libraries/log/src/nrf_log_backend_rtt.c \
  $(SDK_ROOT)/components/libraries/log/src/nrf_log_backend_serial.c \
  $(SDK_ROOT)/components/libraries/log/src/nrf_log_backend_uart.c \
  $(SDK_ROOT)/components/libraries/log/src/nrf_log_default_backends.c \
  $(SDK_ROOT)/components/libraries/log/src/nrf_log_frontend.c \
  $(SDK_ROOT)/components/libraries/log/src/nrf_log_str_formatter.c \
  $(SDK_ROOT)/components/libraries/crypto/nrf_crypto_aead.c \
  $(SDK_ROOT)/components/libraries/crypto/nrf_crypto_aes.c \
  $(SDK_ROOT)/components/libraries/crypto/nrf_crypto_aes_shared.c \
  $(SDK_ROOT)/components/libraries/crypto/nrf_crypto_ecc.c \
  $(SDK_ROOT)/components/libraries/crypto/nrf_crypto_ecdh.c \
  $(SDK_ROOT)/components/libraries/crypto/nrf_crypto_ecdsa.c \
  $(SDK_ROOT)/components/libraries/crypto/nrf_crypto_eddsa.c \
  $(SDK_ROOT)/components/libraries/crypto/nrf_crypto_error.c \
  $(SDK_ROOT)/components/libraries/crypto/nrf_crypto_hash.c \
  $(SDK_ROOT)/components/libraries/crypto/nrf_crypto_hkdf.c \
  $(SDK_ROOT)/components/libraries/crypto/nrf_crypto_hmac.c \
  $(SDK_ROOT)/components/libraries/crypto/nrf_crypto_init.c \
  $(SDK_ROOT)/components/libraries/crypto/nrf_crypto_rng.c \
  $(SDK_ROOT)/components/libraries/crypto/nrf_crypto_shared.c \
  $(PROJ_DIR)/main.c \
  $(SDK_ROOT)/components/softdevice/common/nrf_sdh.c \
  $(SDK_ROOT)/components/softdevice/common/nrf_sdh_ble.c \
  $(SDK_ROOT)/components/softdevice/common/nrf_sdh_soc.c \
  $(SDK_ROOT)/external/mbedtls/library/aes.c \
  $(SDK_ROOT)/external/mbedtls/library/ctr_drbg.c \
  $(SDK_ROOT)/external/mbedtls/library/platform_util.c \
  $(SDK_ROOT)/components/ble/peer_manager/auth_status_tracker.c \
  $(SDK_ROOT)/components/ble/common/ble_advdata.c \
  $(SDK_ROOT)/components/ble/ble_advertising/ble_advertising.c \
  $(SDK_ROOT)/components/ble/common/ble_conn_params.c \
  $(SDK_ROOT)/components/ble/common/ble_conn_state.c \
  $(SDK_ROOT)/components/ble/common/ble_srv_common.c \
  $(SDK_ROOT)/components/ble/peer_manager/gatt_cache_manager.c \
  $(SDK_ROOT)/components/ble/peer_manager/gatts_cache_manager.c \
  $(SDK_ROOT)/components/ble/peer_manager/id_manager.c \
  $(SDK_ROOT)/components/ble/nrf_ble_gatt/nrf_ble_gatt.c \
  $(SDK_ROOT)/components/ble/peer_manager/nrf_ble_lesc.c \
  $(SDK_ROOT)/components/ble/nrf_ble_qwr/nrf_ble_qwr.c \
  $(SDK_ROOT)/components/ble/peer_manager/peer_data_storage.c \
  $(SDK_ROOT)/components/ble/peer_manager/peer_database.c \
  $(SDK_ROOT)/components/ble/peer_manager/peer_id.c \
  $(SDK_ROOT)/components/ble/peer_manager/peer_manager.c \
  $(SDK_ROOT)/components/ble/peer_manager/peer_manager_handler.c \
  $(SDK_ROOT)/components/ble/peer_manager/pm_buffer.c \
  $(SDK_ROOT)/components/ble/peer_manager/security_dispatcher.c \
  $(SDK_ROOT)/components/ble/peer_manager/security_manager.c \
  $(SDK_ROOT)/external/utf_converter/utf.c \
  $(SDK_ROOT)/components/libraries/crypto/backend/oberon/oberon_backend_chacha_poly_aead.c \
  $(SDK_ROOT)/components/libraries/crypto/backend/oberon/oberon_backend_ecc.c \
  $(SDK_ROOT)/components/libraries/crypto/backend/oberon/oberon_backend_ecdh.c \
  $(SDK_ROOT)/components/libraries/crypto/backend/oberon/oberon_backend_ecdsa.c \
  $(SDK_ROOT)/components/libraries/crypto/backend/oberon/oberon_backend_eddsa.c \
  $(SDK_ROOT)/components/libraries/crypto/backend/oberon/oberon_backend_hash.c \
  $(SDK_ROOT)/components/libraries/crypto/backend/oberon/oberon_backend_hmac.c \

# Include folders common to all targets
INC_FOLDERS += \
  -I$(SDK_ROOT)/components/nfc/ndef/generic/message \
  -I$(SDK_ROOT)/components/nfc/t2t_lib \
  -I$(SDK_ROOT)/components/nfc/t4t_parser/hl_detection_procedure \
  -I$(SDK_ROOT)/components/ble/ble_services/ble_ancs_c \
  -I$(SDK_ROOT)/components/ble/ble_services/ble_ias_c \
  -I$(SDK_ROOT)/components/libraries/pwm \
  -I$(SDK_ROOT)/components/softdevice/s132/headers/nrf52 \
  -I$(SDK_ROOT)/external/nrf_oberon/include \
  -I$(SDK_ROOT)/components/libraries/usbd/class/cdc/acm \
  -I$(SDK_ROOT)/components/libraries/usbd/class/hid/generic \
  -I$(SDK_ROOT)/components/libraries/usbd/class/msc \
  -I$(SDK_ROOT)/components/libraries/usbd/class/hid \
  -I$(SDK_ROOT)/modules/nrfx/hal \
  -I$(SDK_ROOT)/components/nfc/ndef/conn_hand_parser/le_oob_rec_parser \
  -I$(SDK_ROOT)/components/libraries/log \
  -I$(SDK_ROOT)/components/ble/ble_services/ble_gls \
  -I$(SDK_ROOT)/components/libraries/fstorage \
  -I$(SDK_ROOT)/components/nfc/ndef/text \
  -I$(SDK_ROOT)/components/libraries/mutex \
  -I$(SDK_ROOT)/components/libraries/gpiote \
  -I$(SDK_ROOT)/components/libraries/bootloader/ble_dfu \
  -I$(SDK_ROOT)/components/nfc/ndef/connection_handover/common \
  -I$(SDK_ROOT)/components/boards \
  -I$(SDK_ROOT)/components/nfc/ndef/generic/record \
  -I$(SDK_ROOT)/components/nfc/t4t_parser/cc_file \
  -I$(SDK_ROOT)/components/ble/ble_advertising \
  -I$(SDK_ROOT)/external/utf_converter \
  -I$(SDK_ROOT)/components/ble/ble_services/ble_bas_c \
  -I$(SDK_ROOT)/components/libraries/crypto/backend/micro_ecc \
  -I$(SDK_ROOT)/modules/nrfx/drivers/include \
  -I$(SDK_ROOT)/components/libraries/experimental_task_manager \
  -I$(SDK_ROOT)/components/ble/ble_services/ble_hrs_c \
  -I$(SDK_ROOT)/components/nfc/ndef/connection_handover/le_oob_rec \
  -I$(SDK_ROOT)/components/libraries/crypto/backend/oberon \
  -I$(SDK_ROOT)/components/libraries/queue \
  -I$(SDK_ROOT)/components/libraries/pwr_mgmt \
  -I$(SDK_ROOT)/components/ble/ble_dtm \
  -I$(SDK_ROOT)/components/toolchain/cmsis/include \
  -I$(SDK_ROOT)/components/ble/ble_services/ble_rscs_c \
  -I$(SDK_ROOT)/components/ble/common \
  -I$(SDK_ROOT)/components/ble/ble_services/ble_lls \
  -I$(SDK_ROOT)/components/nfc/platform \
  -I$(SDK_ROOT)/components/libraries/bsp \
  -I$(SDK_ROOT)/components/libraries/crypto/backend/nrf_hw \
  -I$(SDK_ROOT)/components/nfc/ndef/connection_handover/ac_rec \
  -I$(SDK_ROOT)/components/ble/ble_services/ble_bas \
  -I$(SDK_ROOT)/components/libraries/mpu \
  -I$(SDK_ROOT)/components/libraries/experimental_section_vars \
  -I$(SDK_ROOT)/components/softdevice/s132/headers \
  -I$(SDK_ROOT)/components/ble/ble_services/ble_ans_c \
  -I$(SDK_ROOT)/components/libraries/slip \
  -I$(SDK_ROOT)/components/libraries/delay \
  -I$(SDK_ROOT)/components/libraries/usbd/class/cdc \
  -I$(SDK_ROOT)/components/libraries/memobj \
  -I$(SDK_ROOT)/components/libraries/crypto/backend/cc310_bl \
  -I$(SDK_ROOT)/components/ble/ble_services/ble_nus_c \
  -I$(SDK_ROOT)/components/softdevice/common \
  -I$(SDK_ROOT)/components/ble/ble_services/ble_ias \
  -I$(SDK_ROOT)/components/libraries/usbd/class/hid/mouse \
  -I$(SDK_ROOT)/components/libraries/low_power_pwm \
  -I$(SDK_ROOT)/components/nfc/ndef/conn_hand_parser/ble_oob_advdata_parser \
  -I$(SDK_ROOT)/components/ble/ble_services/ble_dfu \
  -I$(SDK_ROOT)/external/fprintf \
  -I$(SDK_ROOT)/components/libraries/svc \
  -I$(SDK_ROOT)/components/libraries/atomic \
  -I$(SDK_ROOT)/components \
  -I$(SDK_ROOT)/external/nrf_cc310/include \
  -I$(SDK_ROOT)/components/libraries/scheduler \
  -I$(SDK_ROOT)/components/libraries/cli \
  -I$(SDK_ROOT)/components/ble/ble_services/ble_lbs \
  -I$(SDK_ROOT)/components/ble/ble_services/ble_hts \
  -I$(SDK_ROOT)/components/libraries/crc16 \
  -I$(SDK_ROOT)/components/nfc/t4t_parser/apdu \
  -I$(SDK_ROOT)/components/libraries/util \
  -I../config \
  -I$(SDK_ROOT)/components/libraries/csense_drv \
  -I$(SDK_ROOT)/components/libraries/csense \
  -I$(SDK_ROOT)/components/libraries/balloc \
  -I$(SDK_ROOT)/components/libraries/ecc \
  -I$(SDK_ROOT)/components/libraries/hardfault \
  -I$(SDK_ROOT)/components/ble/ble_services/ble_cscs \
  -I$(SDK_ROOT)/components/libraries/hci \
  -I$(SDK_ROOT)/components/libraries/usbd/class/hid/kbd \
  -I$(SDK_ROOT)/components/libraries/timer \
  -I$(SDK_ROOT)/integration/nrfx \
  -I$(SDK_ROOT)/components/libraries/stack_info \
  -I$(SDK_ROOT)/components/nfc/t4t_parser/tlv \
  -I$(SDK_ROOT)/components/libraries/sortlist \
  -I$(SDK_ROOT)/components/libraries/spi_mngr \
  -I$(SDK_ROOT)/components/libraries/led_softblink \
  -I$(SDK_ROOT)/components/nfc/ndef/conn_hand_parser \
  -I$(SDK_ROOT)/components/libraries/sdcard \
  -I$(SDK_ROOT)/components/nfc/t4t_lib \
  -I$(SDK_ROOT)/components/nfc/ndef/parser/record \
  -I$(SDK_ROOT)/modules/nrfx/mdk \
  -I$(SDK_ROOT)/components/ble/ble_services/ble_cts_c \
  -I$(SDK_ROOT)/external/nrf_tls/mbedtls/nrf_crypto/config \
  -I$(SDK_ROOT)/components/ble/ble_services/ble_nus \
  -I$(SDK_ROOT)/components/libraries/twi_mngr \
  -I$(SDK_ROOT)/components/ble/ble_services/ble_hids \
  -I$(SDK_ROOT)/components/libraries/strerror \
  -I$(SDK_ROOT)/components/libraries/crc32 \
  -I$(SDK_ROOT)/components/nfc/ndef/connection_handover/ble_oob_advdata \
  -I$(SDK_ROOT)/components/nfc/t2t_parser \
  -I$(SDK_ROOT)/components/nfc/ndef/connection_handover/ble_pair_msg \
  -I$(SDK_ROOT)/components/libraries/crypto/backend/optiga \
  -I$(SDK_ROOT)/components/libraries/usbd/class/audio \
  -I$(SDK_ROOT)/components/libraries/sensorsim \
  -I$(SDK_ROOT)/components/libraries/crypto/backend/nrf_sw \
  -I$(SDK_ROOT)/components/ble/peer_manager \
  -I$(SDK_ROOT)/components/libraries/mem_manager \
  -I$(SDK_ROOT)/components/libraries/ringbuf \
  -I$(SDK_ROOT)/components/ble/ble_services/ble_tps \
  -I$(SDK_ROOT)/components/ble/ble_services/ble_rscs \
  -I$(SDK_ROOT)/components/nfc/ndef/parser/message \
  -I$(SDK_ROOT)/components/libraries/crypto/backend/mbedtls \
  -I$(SDK_ROOT)/components/libraries/crypto/backend/cc310 \
  -I$(SDK_ROOT)/external/nrf_oberon \
  -I$(SDK_ROOT)/components/ble/ble_services/ble_dis \
  -I$(SDK_ROOT)/components/nfc/ndef/uri \
  -I$(SDK_ROOT)/components/ble/nrf_ble_gatt \
  -I$(SDK_ROOT)/components/ble/nrf_ble_qwr \
  -I$(SDK_ROOT)/components/libraries/gfx \
  -I$(SDK_ROOT)/components/libraries/button \
  -I$(SDK_ROOT)/modules/nrfx \
  -I$(SDK_ROOT)/components/libraries/twi_sensor \
  -I$(SDK_ROOT)/integration/nrfx/legacy \
  -I$(SDK_ROOT)/components/libraries/usbd \
  -I$(SDK_ROOT)/external/mbedtls/include \
  -I$(SDK_ROOT)/components/nfc/ndef/connection_handover/ep_oob_rec \
  -I$(SDK_ROOT)/external/segger_rtt \
  -I$(SDK_ROOT)/components/libraries/atomic_fifo \
  -I$(SDK_ROOT)/components/ble/ble_services/ble_lbs_c \
  -I$(SDK_ROOT)/components/nfc/ndef/connection_handover/ble_pair_lib \
  -I$(SDK_ROOT)/components/libraries/crypto \
  -I$(SDK_ROOT)/components/ble/ble_racp \
  -I$(SDK_ROOT)/components/libraries/fds \
  -I$(SDK_ROOT)/components/nfc/ndef/launchapp \
  -I$(SDK_ROOT)/components/libraries/atomic_flags \
  -I$(SDK_ROOT)/components/ble/ble_services/ble_hrs \
  -I$(SDK_ROOT)/components/libraries/crypto/backend/cifra \
  -I$(SDK_ROOT)/components/nfc/ndef/connection_handover/hs_rec \
  -I$(SDK_ROOT)/components/nfc/ndef/conn_hand_parser/ac_rec_parser \
  -I$(SDK_ROOT)/components/libraries/stack_guard \
  -I$(SDK_ROOT)/components/libraries/log/src \
 
# Libraries common to all targets
LIB_FILES += \
  $(SDK_ROOT)/external/nrf_cc310/lib/cortex-m4/hard-float/libnrf_cc310_0.9.13.a \
  $(SDK_ROOT)/external/nrf_oberon/lib/cortex-m4/hard-float/liboberon_3.0.6.a \

# Optimization flags
OPT = -O3 -g3
# Uncomment the line below to enable link time optimization
#OPT += -flto

# C flags common to all targets
CFLAGS += $(OPT)
CFLAGS += -DAPP_TIMER_V2
CFLAGS += -DAPP_TIMER_V2_RTC1_ENABLED
CFLAGS += -DBLE_STACK_SUPPORT_REQD
CFLAGS += -DBOARD_PCA10040
CFLAGS += -DCONFIG_GPIO_AS_PINRESET
CFLAGS += -DFLOAT_ABI_HARD
CFLAGS += -DMBEDTLS_CONFIG_FILE=\"nrf_crypto_mbedtls_config.h\"
CFLAGS += -DNRF52
CFLAGS += -DNRF52832_XXAA
CFLAGS += -DNRF52_PAN_74
CFLAGS += -DNRF_CRYPTO_MAX_INSTANCE_COUNT=1
CFLAGS += -DNRF_SD_BLE_API_VERSION=7
CFLAGS += -DS132
CFLAGS += -DSOFTDEVICE_PRESENT
CFLAGS += -mcpu=cortex-m4
CFLAGS += -mthumb -mabi=aapcs
CFLAGS += -Wall -Werror
CFLAGS += -mfloat-abi=hard -mfpu=fpv4-sp-d16
# keep every function in a separate section, this allows linker to discard unused ones
CFLAGS += -ffunction-sections -fdata-sections -fno-strict-aliasing
CFLAGS += -fno-builtin -fshort-enums
CFLAGS += $(INC_FOLDERS)

# ASMFLAGS += $(INC_FOLDERS)
# C++ flags common to all targets
CXXFLAGS += $(OPT)
# Assembler flags common to all targets
ASMFLAGS += -g3
ASMFLAGS += -mcpu=cortex-m4
ASMFLAGS += -mthumb -mabi=aapcs
ASMFLAGS += -mfloat-abi=hard -mfpu=fpv4-sp-d16
ASMFLAGS += -DAPP_TIMER_V2
ASMFLAGS += -DAPP_TIMER_V2_RTC1_ENABLED
ASMFLAGS += -DBLE_STACK_SUPPORT_REQD
ASMFLAGS += -DBOARD_PCA10040
ASMFLAGS += -DCONFIG_GPIO_AS_PINRESET
ASMFLAGS += -DFLOAT_ABI_HARD
ASMFLAGS += -DNRF52
ASMFLAGS += -DNRF52832_XXAA
ASMFLAGS += -DNRF52_PAN_74
ASMFLAGS += -DNRF_CRYPTO_MAX_INSTANCE_COUNT=1
ASMFLAGS += -DNRF_SD_BLE_API_VERSION=7
ASMFLAGS += -DS132
ASMFLAGS += -DSOFTDEVICE_PRESENT

# Linker flags
LDFLAGS += $(OPT)
LDFLAGS += -mthumb -mabi=aapcs -L$(SDK_ROOT)/modules/nrfx/mdk -T$(LINKER_SCRIPT)
LDFLAGS += -mcpu=cortex-m4
LDFLAGS += -mfloat-abi=hard -mfpu=fpv4-sp-d16
# let linker dump unused sections
LDFLAGS += -Wl,--gc-sections
# use newlib in nano version
LDFLAGS += --specs=nano.specs

# nrf52832_xxaa: CFLAGS += -D__HEAP_SIZE=8192
# nrf52832_xxaa: CFLAGS += -D__STACK_SIZE=8192
# nrf52832_xxaa: ASMFLAGS += -D__HEAP_SIZE=8192
# nrf52832_xxaa: ASMFLAGS += -D__STACK_SIZE=8192
CFLAGS += -D__HEAP_SIZE=8192
CFLAGS += -D__STACK_SIZE=8192
ASMFLAGS += -D__HEAP_SIZE=8192
ASMFLAGS += -D__STACK_SIZE=8192



# Add standard libraries at the very end of the linker input, after all objects
# that may need symbols provided by these libraries.
LIB_FILES += -lc -lnosys -lm


OBJECTS = $(addprefix $(BUILD)/,$(notdir $(SRC_FILES:.c=.o))) #指定.o文件生成目录
vpath %.c $(sort $(dir $(SRC_FILES))) #例如在后续的%.o:%.c规则中，make会自动去指定目录下查找

OBJECTS += $(addprefix $(BUILD)/,$(notdir $(S_SOURCES:%.S=%.o)))
vpath %.S $(sort $(dir $(S_SOURCES)))

all:$(BUILD)/$(TARGETS).out $(BUILD)/$(TARGETS).hex $(BUILD)/$(TARGETS).bin

$(BUILD)/%.o : %.c | $(BUILD)
	@$(CC) $(CFLAGS) -c $< -o $@
$(BUILD)/%.o : %.S | $(BUILD)
	@$(AS)  -c $< -o $@
#  @echo $(notdir $(<:.s=.o))
$(BUILD)/$(TARGETS).out : $(OBJECTS)
	$(CC)  $(LDFLAGS) $^ $(LIBDIR) $(LIB_FILES) -o $@
	$(SZ) $@
$(BUILD)/%.hex: $(BUILD)/%.out | $(BUILD)
	$(HEX) $< $@
$(BUILD)/%.bin: $(BUILD)/%.out | $(BUILD)
	$(BIN) $< $@

-include $(wildcard $(BUILD)/*.d)

#创建build 文件夹
$(BUILD):
	mkdir $@
clean:
	rm -rf $(BUILD)







# .PHONY: default help

# # Default target - first one defined
# default: nrf52832_xxaa

# # Print all targets that can be built
# help:
# 	@echo following targets are available:
# 	@echo		nrf52832_xxaa
# 	@echo		flash_softdevice
# 	@echo		sdk_config - starting external tool for editing sdk_config.h
# 	@echo		flash      - flashing binary

# TEMPLATE_PATH := $(SDK_ROOT)/components/toolchain/gcc


# include $(TEMPLATE_PATH)/Makefile.common

# $(foreach target, $(TARGETS), $(call define_target, $(target)))



# .PHONY: flash flash_softdevice erase

# # Flash the program
# flash: default
# 	@echo Flashing: $(BUILD)/nrf52832_xxaa.hex
# 	nrfjprog -f nrf52 --program $(BUILD)/nrf52832_xxaa.hex --sectorerase
# 	nrfjprog -f nrf52 --reset

# # Flash softdevice
# flash_softdevice:
# 	@echo Flashing: s132_nrf52_7.2.0_softdevice.hex
# 	nrfjprog -f nrf52 --program $(SDK_ROOT)/components/softdevice/s132/hex/s132_nrf52_7.2.0_softdevice.hex --sectorerase
# 	nrfjprog -f nrf52 --reset

# erase:
# 	nrfjprog -f nrf52 --eraseall
# .PHONY:clean
# 	-rm -fR _build

  
# SDK_CONFIG_FILE := ../config/sdk_config.h
# CMSIS_CONFIG_TOOL := $(SDK_ROOT)/external_tools/cmsisconfig/CMSIS_Configuration_Wizard.jar
# sdk_config:
# 	java -jar $(CMSIS_CONFIG_TOOL) $(SDK_CONFIG_FILE)

down:
	openocd -f stlink-v2.cfg -f nrf52.cfg -c "init" -c "reset halt" -c "flash write_image erase _build/nrf52832_xxaa.hex" -c reset -c shutdown
ocd:
	openocd -f stlink-v2.cfg -f nrf52.cfg
