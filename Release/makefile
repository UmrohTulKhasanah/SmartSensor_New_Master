################################################################################
# Automatically-generated file. Do not edit!
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include myUART/subdir.mk
-include mySPI/subdir.mk
-include subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(ASM_DEPS)),)
-include $(ASM_DEPS)
endif
ifneq ($(strip $(S_DEPS)),)
-include $(S_DEPS)
endif
ifneq ($(strip $(S_UPPER_DEPS)),)
-include $(S_UPPER_DEPS)
endif
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
endif

-include ../makefile.defs

# Add inputs and outputs from these tool invocations to the build variables 
LSS += \
WML_SmartSensor_Master.lss \

FLASH_IMAGE += \
WML_SmartSensor_Master.hex \

EEPROM_IMAGE += \
WML_SmartSensor_Master.eep \

SIZEDUMMY += \
sizedummy \


# All Target
all: WML_SmartSensor_Master.elf secondary-outputs

# Tool invocations
WML_SmartSensor_Master.elf: $(OBJS) $(USER_OBJS)
	@echo 'Building target: $@'
	@echo 'Invoking: AVR C Linker'
	avr-gcc -Wl,-Map,WML_SmartSensor_Master.map -mmcu=atmega328p -o "WML_SmartSensor_Master.elf" $(OBJS) $(USER_OBJS) $(LIBS)
	@echo 'Finished building target: $@'
	@echo ' '

WML_SmartSensor_Master.lss: WML_SmartSensor_Master.elf
	@echo 'Invoking: AVR Create Extended Listing'
	-avr-objdump -h -S WML_SmartSensor_Master.elf  >"WML_SmartSensor_Master.lss"
	@echo 'Finished building: $@'
	@echo ' '

WML_SmartSensor_Master.hex: WML_SmartSensor_Master.elf
	@echo 'Create Flash image (ihex format)'
	-avr-objcopy -R .eeprom -R .fuse -R .lock -R .signature -O ihex WML_SmartSensor_Master.elf  "WML_SmartSensor_Master.hex"
	@echo 'Finished building: $@'
	@echo ' '

WML_SmartSensor_Master.eep: WML_SmartSensor_Master.elf
	@echo 'Create eeprom image (ihex format)'
	-avr-objcopy -j .eeprom --no-change-warnings --change-section-lma .eeprom=0 -O ihex WML_SmartSensor_Master.elf  "WML_SmartSensor_Master.eep"
	@echo 'Finished building: $@'
	@echo ' '

sizedummy: WML_SmartSensor_Master.elf
	@echo 'Invoking: Print Size'
	-avr-size --format=berkeley -t WML_SmartSensor_Master.elf
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) $(FLASH_IMAGE)$(ELFS)$(OBJS)$(ASM_DEPS)$(EEPROM_IMAGE)$(S_DEPS)$(SIZEDUMMY)$(S_UPPER_DEPS)$(LSS)$(C_DEPS) WML_SmartSensor_Master.elf
	-@echo ' '

secondary-outputs: $(LSS) $(FLASH_IMAGE) $(EEPROM_IMAGE) $(SIZEDUMMY)

.PHONY: all clean dependents

-include ../makefile.targets
